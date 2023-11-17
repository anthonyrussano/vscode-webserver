# code-server

This repo allows you to run a local VSCode server.

It consists of a standalone binary that can be run as a service.

When configured correctly, it should initiate a download of the latest version of VSCode.

## Usage

- Place the, `code-server-standalone` binary in the following location: `/usr/local/bin/`.
- Make the binary executable: `sudo chmod a+x /usr/local/bin/code-server-standalone`
- Test running a local VSCode Server:
  - `code-server-standalone --disable-telemetry --accept-server-license-terms serve-local --host 0.0.0.0 --without-connection-token`
- To run this as a service:

```bash
nano /etc/systemd/system/code-server.service
```

```
[Unit]
Description=Code Server Service

[Service]
ExecStart=/usr/local/bin/code-server-standalone --disable-telemetry --accept-server-license-terms --server-data-dir <optional-parameter> serve-local --host 0.0.0.0 --without-connection-token
User=user
Restart=always
LimitNOFILE=20480

[Install]
WantedBy=multi-user.target
```
Then enable and start the service:
```
sudo systemctl daemon-reload
sudo systemctl enable code-server
sudo systemctl start code-server
sudo systemctl status code-server
```
Ensure that the User directive is correctly set. The user should have appropriate permissions for the specified paths and executables.
