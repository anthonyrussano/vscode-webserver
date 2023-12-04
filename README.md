# vscode-webserver

This repo allows you to run VSCode as a local webserver.

## Usage

For Linux environments:

- Place the `code-server` binary file in the following location: `/usr/local/bin/`.
- Place the `code-server.service` file in the following location: `/etc/systemd/system/`.
  - You may need to edit the `code-server.service` according to your specific environment.
    - This may include changing the User directive value and/or adding additional parameters to ExecStart.
- Enable and start the service:
  - `sudo systemctl daemon-reload`
  - `sudo systemctl enable code-server`
  - `sudo systemctl start code-server`
  - `sudo systemctl status code-server`
- The vscode server should be accessible at the following url:
  - http://localhost:8000/

### For Windows 

This binary should also work on windows... Just open up powershell and type the following command:

- `code-server --disable-telemetry --accept-server-license-terms serve-local --host 0.0.0.0 --without-connection-token`

## References

I obtained the `code-server` binary from the following setup script provided by Microsoft:

- https://vscodeserverlauncher.blob.core.windows.net/builds/setup-scripts/setup.sh

Part of the script downloads the binary from the following location:

- `INSTALL_URL=https://aka.ms/vscode-server-launcher/$INSTALL_ARCH-$INSTALL_TARGET`

The original article that referenced this setup script can be found here:

- https://code.visualstudio.com/blogs/2022/07/07/vscode-server
