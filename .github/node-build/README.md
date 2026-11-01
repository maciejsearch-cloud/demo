# Zależności budowania węzła na PC

Pliki `<plat>.txt` przypinają każdą paczkę (także zależności pośrednie) do dokładnej wersji i skrótu SHA-256;
workflow instaluje je przez `pip install --require-hashes`, więc podmieniona paczka na PyPI / w indeksie PyTorch
przerywa budowanie zamiast trafić do pliku wykonywalnego.

Odświeżanie (Python 3.12, `uv`):

```bash
cd .github/node-build
CPU="--index-url https://download.pytorch.org/whl/cpu --extra-index-url https://pypi.org/simple --index-strategy unsafe-best-match"
uv pip compile base.in --generate-hashes --python-version 3.12 --python-platform x86_64-unknown-linux-gnu $CPU -o linux.txt
uv pip compile base.in --generate-hashes --python-version 3.12 --python-platform x86_64-pc-windows-msvc $CPU -o windows.txt
uv pip compile base.in --generate-hashes --python-version 3.12 --python-platform aarch64-apple-darwin -o macos.txt
uv pip compile windows-directml.in --generate-hashes --python-version 3.12 --python-platform x86_64-pc-windows-msvc -o windows-directml.txt
```
