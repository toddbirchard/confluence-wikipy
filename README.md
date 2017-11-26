# Confluence Hierarchy Builder
Generates a hierarchy of Confluence pages in a tree format using Python 2.7.X.

Confluence Hierarchy Builder is useful for large Confluence instances which have grown past the point of reasonable maintence. While Atlassian supports HTML, XML, and PDF exports of Confluence, these exports exist only on a per-space or per-page basis. For organizations with hundreds of spaces (which is fairly common) there is no other tool which allows users to build a visual heirarchy of their own Confluence.

## Example output
![Output Example](https://s3.us-east-2.amazonaws.com/toddbirchard-github/Confluence+Hierarchy/output3.png)

## Dependencies
1. Confluence Python CLI: https://github.com/RaymiiOrg/confluence-python-cli
2. Pandas: https://pandas.pydata.org/
3. Treelib: http://treelib.readthedocs.io/en/latest/install.html
4. A user with access to the target Confluence instance

## Usage
1. Use Confluence Python CLI to generate a CSV of pages from your Confluence instance":

   python confluence.py --help                                                                                         
   confluence.py [-h] -w WIKIURL -u USERNAME -p PASSWORD
   
   {addpage, updatepage, listpages, removepage, getpagecontent, getpagesummary, listspaces, addspace, removespace, adduser,    removeuser, deactivateuser, reactivateuser, changeuserpassword, addgroup, removegroup, listgroups, listusers, 
   getallpages, addusertogroup, removeusergromgroup, listusergroups}

2. Add labels to generated CSV

    Ensure this follows the format: 'id', 'space', 'parent', 'name', 'url'
    NOTE: Check CSV to ensure data is not broken; commas in page titles will break the CSV.

4. Run 'python confTree.py'

    As long as the generated CSV is formatted correctly and lives in the same directory as confTree.py, this should run as  expected.

## Things to note
- Ensure that the contents of 'listpages' (from confluence.py) are saved as a file named confluence.csv (this should replace the example confluence.csv provided here)
- Confluence Hierarchy Builder builds four heirarchies deep into each space, but can be easily modified to include more
- A Confluence instance of 10,000 pages will take roughly 10-15 minutes to process

# Coming updates
- Python 3 support
- Flask web interface
- Documentation of source code
- Detect number of hierarchies
- Built-in API handling

