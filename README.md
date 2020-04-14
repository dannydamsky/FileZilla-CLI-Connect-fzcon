# FileZilla CLI Connect (fzcon)
Helper script to automatically connect to site entries stored in FileZilla using SSH and SFTP.

# Dependencies
- SSH Client
- sshpass
- column
- FileZilla

# Arguments
1. Entry name (snake_case)
2. Connection Type (default is SSH, options include: --sftp, --tunnel)
3. Tunnel Port, only used if the second argument is --tunnel, default is 8888.

# Installation
Put the fzcon script in /usr/local/bin, make sure it has execute privileges.

# ZSH Auto-Complete

Add this block to $HOME/.zshrc:

    _fzcon_autocomplete() {
            reply=($(fzcon | cut -f1 -d ' ' | sed '1d'));
    }

    compctl -K _fzcon_autocomplete fzcon;
