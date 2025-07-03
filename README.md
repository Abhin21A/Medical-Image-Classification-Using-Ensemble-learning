# Let's inspect the uploaded Jupyter notebook to understand its contents
import nbformat

# Load the notebook
notebook_path = "/mnt/data/resnet50_medical.ipynb"
with open(notebook_path, 'r', encoding='utf-8') as f:
    notebook = nbformat.read(f, as_version=4)

# Extract all code cells and a preview of markdown for summary
code_cells = [cell['source'] for cell in notebook.cells if cell['cell_type'] == 'code']
markdown_cells = [cell['source'] for cell in notebook.cells if cell['cell_type'] == 'markdown']

# Give a short preview for analysis
code_preview = code_cells[:2]  # show the first 2 code cells
markdown_preview = markdown_cells[:2]  # show the first 2 markdown cells

code_preview, markdown_preview
