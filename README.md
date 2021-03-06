# FileZilla CLI Connect (fzcon)
Helper script to automatically connect to site entries stored in FileZilla using SSH and SFTP.

# Dependencies
- SSH Client (Such as OpenSSL)
- sshpass
- column
- base64
- FileZilla

# Arguments
1. Entry name (snake_case)
2. Connection Type (default is SSH, options include: --sftp, --tunnel)
3. Tunnel Port, only used if the second argument is --tunnel, default is 8888.

Not passing any arguments to the utility will make the utility print out the available
options.

# Installation
Put the fzcon script in /usr/local/bin, make sure it has execute privileges.

# ZSH Auto-Complete

Add this block to $HOME/.zshrc:

    _fzcon_autocomplete() {
            reply=($(fzcon | cut -f1 -d ' ' | sed '1d'));
    }

    compctl -K _fzcon_autocomplete fzcon;

# Developer
Danny Damsky <dannydamsky99@gmail.com>

# Licence
Copyright (c) 2020 Danny Damsky

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:
1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.
3. Neither the name of the author nor the names of its contributors may
   be used to endorse or promote products derived from this software

THIS SOFTWARE IS PROVIDED BY THE AUTHOR AND CONTRIBUTORS ``AS IS'' AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED.  IN NO EVENT SHALL THE AUTHOR OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS
OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY
OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF
SUCH DAMAGE.
