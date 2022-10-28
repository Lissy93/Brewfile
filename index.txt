#!/bin/bash

######################################################################
# 🍺 Lissy93/Brewfile - All-in-one install script                    #
######################################################################
# Sets up Homebrew, downloads Brewfile, and bundles listed packages  #
# IMPORTANT: Before running, read through everything very carefully! #
# Licensed under MIT (C) Alicia Sykes 2022 <https://aliciasykes.com> #
######################################################################

# User-specified config
BREWFILE_LOCATION="${HOME}/.Brewfile"
REMOTE_BREWFILE="https://raw.githubusercontent.com/Lissy93/Brewfile/HEAD/Brewfile"

# General config
PARAMS=$* # User-specified parameters
CURRENT_DIR=$(cd "$(dirname ${BASH_SOURCE[0]})" && pwd)
PROMPT_TIMEOUT=15 # When user is prompted for input, skip after x seconds
START_TIME=`date +%s` # Start timer

# Color Variables
HEADING_COLOR='\033[1;96m'
QUESTION_COLOR='\033[1;93m'
INFO_COLOR='\033[0;33m\x1b[2m'
ERROR_COLOR='\033[1;31m'
RESET='\033[0m'

install_homebrew () {
  echo -en "\n🍺  ${HEADING_COLOR}Installing Homebrew${RESET}\n"
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  export PATH=/opt/homebrew/bin:$PATH
}

download_brewfile () {
  echo -en "\n📥  ${HEADING_COLOR}Downloading Brewfile${RESET}\n"
  if hash "curl" 2> /dev/null; then
    curl -o $BREWFILE_LOCATION  $REMOTE_BREWFILE
  elif hash "wget" 2> /dev/null; then
    wget -O $BREWFILE_LOCATION $REMOTE_BREWFILE
  else
    echo -e "${ERROR_COLOR}Error: Either curl or wget is required to download the Brewfile${RESET}"
    exit 1
  fi
}

update_packages () {
  echo -en "\n⤴️  ${HEADING_COLOR}Updating packages${RESET}\n"
  brew update # Update Brew to latest version
  brew upgrade # Upgrade all installed casks
}

edit_brewfile () {
  editor=${VISUAL-${EDITOR-nano}}
  echo -en "\n📝  ${HEADING_COLOR}Opening Brewfile in ${editor}${RESET}"
  ${editor} $BREWFILE_LOCATION
}

install_apps () {
  echo -en "\n💾  ${HEADING_COLOR}Installing listed apps${RESET}\n"
  brew bundle --global --file $BREWFILE_LOCATION
}

show_intro () {
  echo -e "\n${QUESTION_COLOR}🍺 Lissy93/Brewfile - Installation Script${RESET}"
  echo -e "${INFO_COLOR}The following steps will be taken:"
  echo "- Check Homebrew is installed, prompt to download if not"
  echo "- If no Brewfile present, download from GitHub, othwesise prompt user"
  echo "- Update Homebrew and upgrade currently installed packages"
  echo "- Ask user if they wish to edit Brewfile before continuing"
  echo "- Install and bundle all packages listed in the Brewfile"
  echo "- Print a summary of changes made and time taken"
  echo -e "${RESET}"
}

# If set to auto-yes - then don't wait for user reply
if [[ $PARAMS == *"--auto-yes"* ]]; then
  PROMPT_TIMEOUT=1
  REPLY='Y'
fi

# If --help flag passed, show intro and exit
if [[ $PARAMS == *"--help"* ]]; then
  show_intro
  exit 
fi

show_intro

# Check that Homebrew is installed, offer to install it if not present
if ! hash "brew" 2> /dev/null; then
  echo -e "\n${QUESTION_COLOR}Homebrew isn't present on this system. Would you like to install it now? (y/N)${RESET}"
  read -t $PROMPT_TIMEOUT -n 1 -r
  if [[ $REPLY =~ ^[Yy]$ ]]; then
    install_homebrew
  fi
fi

# Check that Brewfile isn't already present, then download
if [ -f $BREWFILE_LOCATION ]; then
  echo -e "\n${QUESTION_COLOR}Brewfile already exists. Would you like to overwrite it? (y/N)${RESET}"
  read -t $PROMPT_TIMEOUT -n 1 -r
    if [[ $REPLY =~ ^[Yy]$ ]]; then
      download_brewfile
    fi
else
  download_brewfile
fi

# Run brew update and upgrade
echo -e "\n${QUESTION_COLOR}Update and upgrade existing packages first? (y/N)${RESET}"
read -t $PROMPT_TIMEOUT -n 1 -r
if [[ $REPLY =~ ^[Yy]$ ]]; then
  update_packages
fi

# Ask user if they'd like to edit the Brewfile before bundling
echo -e "\n${QUESTION_COLOR}Would you like to edit the Brewfile before installing packages? (y/N)${RESET}"
read -t $PROMPT_TIMEOUT -n 1 -r should_edit
if [[ $should_edit =~ ^[Yy]$ ]]; then
  edit_brewfile
fi

# Confirm user is happy to proceed with package installations
echo -e "\n${QUESTION_COLOR}Proceed with installing listed packages? (y/N)${RESET}"
read -t $PROMPT_TIMEOUT -n 1 -r
if [[ $REPLY =~ ^[Yy]$ ]]; then
  install_apps
fi

# Print finishing off message
echo -e "\n✅ ${HEADING_COLOR}Tasks completed sucesfully in $((`date +%s`-START_TIME)) seconds${RESET}"
echo -e "\x1b[2m\n.~~~~.\n\033[0;33m\x1b[2mi====i_\n|cccc|_)\n|cccc|\n\`-==-'\n${RESET}"
echo -e "\033[0;33m\x1b[2mThank you for using Lissy93/Brewfile${RESET}"
unset PROMPT_TIMEOUT
unset REPLY

# EOF
