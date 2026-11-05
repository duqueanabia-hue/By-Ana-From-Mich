# By-Ana-From-Mich
from pathlib import Path

path = Path("/mnt/data/nosso_cantinho_michelly.html")
if not path.exists():
    raise FileNotFoundError("Não encontrei o arquivo original do site nesta sessão.")

html = path.read_text(encoding="utf-8")
html = html.replace('const START_DATE = "2025-12-21";', 'const START_DATE = "2025-12-21"; // Data oficial confirmada: 21/12/2025')
html = html.replace('Extra Bom', 'extra bom')
html = html.replace('EXTRA BOM', 'extra bom')
updated = Path("/mnt/data/nosso_cantinho_michelly_atualizado.html")
updated.write_text(html, encoding="utf-8")
print("Site atualizado com a data oficial de namoro: 21/12/2025.")
print(f"Arquivo: {updated}")
