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
