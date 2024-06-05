This project demonstrates the creation of malware findings for [known-malicious packages](https://osv.dev/list?q=MAL).

# Python

Dependencies are declared in `requirements.txt`.

Since the malicious package [aiohtt](https://osv.dev/vulnerability/MAL-2023-1578) has been removed from PyPI, it has been copied into the repo (the malicious code being removed) and you need to serve it using a [local registry](https://stackoverflow.com/questions/18052217/how-can-i-create-a-local-own-pypi-repository-index-without-a-mirror#18476794).
```
cd repodir
python3 -m http.server 9000
```

Then open another terminal, go the repo root directory and run:
```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt --extra-index-url=http://127.0.0.1:9000
```

Links:
- https://packaging.python.org/en/latest/guides/hosting-your-own-index/

Other malicious or suspicious packages useful for demo purposes:

- Known malicious ([not available](https://pypi.org/project/azureml-contrib-daskonbatch) anymore on PyPI): [azureml-contrib-daskonbatch](https://osv.dev/vulnerability/MAL-2023-8563)
- Suspicious
    - [smartchart](https://inspector.pypi.io/project/smartchart/6.7.1/packages/e7/d0/451e376716eeebd38e19403ed76523782243147084baa6caa83644d0ccbd/smartchart-6.7.1.tar.gz/smartchart-6.7.1/smart_chart/echart/admin.py)
    - [areixio](https://inspector.pypi.io/project/areixio/0.3.11/packages/de/73/3759bcca860a966c927d617266e05591882244e2943151edcce54fe4df97/areixio-0.3.11.tar.gz/areixio-0.3.11/areixio/exchanges/ivOEiHrDQySFXpdnhoQXAgosAUoxMNhw.py)
    - [always-updates](https://inspector.pypi.io/project/always-updates/156.7/packages/17/69/0e01ef4bbd8724710ff548950d357a6a30b197c4f94cb3a30cec01edd583/always_updates-156.7.tar.gz/always_updates-156.7/always_updates/__main__.py)

# JavaScript