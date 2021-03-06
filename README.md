# Isogeo User oAuth2 example - Website with Flask

Sample project to illustrate how to authentifiy to Isogeo API with Authorization Code Grant flow

> *DO NOT USE THIS CODE IN PRODUCTION*

## Usage

Install:

1. Clone/download this [repository](https://github.com/isogeo/api-sample-oauth2-agf-py),
2. Paste your `client_secrets.json` file
3. Open a prompt (bash, powershell...),
4. Create autosigned SSL certififcate/key pair ([for Windows users, see this page [fr]](https://github.com/isogeo/isogeo-manager/wiki/setup) )

    ```bash
    mkdir certs
    openssl req -nodes -new -x509 -keyout certs/server.key -out certs/server.cert
    ```

5. Then, depending on your flavour...

### With your installed Python

1. Create a virtualenv and install prerequisites:

    ```powershell
    py -3 -m  venv env
    pip install --upgrade -r requirements.txt
    # or if you have pipenv
    pipenv install --dev
    ```

2. Run it:

    ```powershell
    Set-Item Env:FLASK_APP ".\runserver.py"
    flask run
    ```

3. Open your favorite browser to <https://localhost:3000>.

### With Docker

```powershell
# build the container
docker build -t isogeo-api-sample-oauth2-agf-py:latest .
# launch it in detached mode
docker run --rm --name isogeo-websample -d -p 3000:3000 isogeo-oauth2-sample
```

Then, open your favorite browser to <https://localhost:3000>.
