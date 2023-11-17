# vscode-webserver

This repo allows you to run VSCode as a local webserver.

## Usage

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
