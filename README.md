# Confluence Hierarchy Builder
Generates a hierarchy of Confluence pages in a tree format using Python 2.7.X.

Example output:
![Output Example](https://s3.us-east-2.amazonaws.com/toddbirchard-github/Confluence+Hierarchy/output.png)

## Dependencies
1. Confluence Python CLI: https://github.com/RaymiiOrg/confluence-python-cli
2. Pandas: https://pandas.pydata.org/
3. http://treelib.readthedocs.io/en/latest/install.html
4. A user with access to the target Confluence instance

## Usage
1. Use Confluence Python CLI to generate a CSV of pages from your Confluence instance
2. Add labels to CSV: 'id', 'space', 'parent', 'name', 'url'
3. Ensure CSV lives in same directory as conf.py
4. CD to directory
5. Run 'python confTree.py'

## Things to note
- Ensure that the contents of 'listpages' from confluence.py are saved as a file named confluence.csv
- Confluence Hierarchy Builder currently builds three heirarchies deep into each space, but is easily modified to include more
- A Confluence instance of 10,000 pages will take roughly 10-15 minutes to process

## Purpose
Confluence Hierarchy Builder is exceptionally useful for large COnfluence instances which have grown past the point of reasonable maintence. While Atlassian supports HTML, XML, and PDF exports of Confluence, these exports exist only on a per-space or per-page basis. For organizations with hundreds of spaces (fairly common), there is no other tool which allows users to build a visual heirarchy of their own Confluence as a whole.

# Coming updates
- A visual interface
- In-depth instructions and explanations of source code
- Support for a variable number of hierarchies
