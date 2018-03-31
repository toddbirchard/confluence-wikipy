# Wikipy

![python badge](https://img.shields.io/badge/python-3.6-blue.svg?longCache=true&style=flat-square) ![pandas badge](https://img.shields.io/badge/pandas-0.22.0-blue.svg?longCache=true&style=flat-square) ![treelib badge](https://img.shields.io/badge/treelib-1.4.0-blue.svg?longCache=true&style=flat-square) ![xmlrpc badge](https://img.shields.io/badge/xmlrpc.client-21.26.-blue.svg?longCache=true&style=flat-square) ![MIT badge](https://img.shields.io/badge/license-MIT-green.svg?longCache=true&style=flat-square) ![Confluence badge](https://img.shields.io/badge/platform-Confluence-lightgray.svg?longCache=true&style=flat-square)

Python 3 CLI for interacting with Confluence API.

Wikipy's tree builder is useful for large Confluence instances which have grown past the point of reasonable maintence. While Atlassian supports HTML, XML, and PDF exports of Confluence, these exports exist only on a per-space or per-page basis. For organizations with hundreds of spaces (which is fairly common) there is no other tool which allows users to build a visual heirarchy of their own Confluence.

## Example output
├── **Meaty Meats**    
│   ├── Spicy jalapeno bacon ipsum dolor amet chicken doner corned beef sirloin   
│   ├── Hamburger picanha cow pork chop chicken   
│   ├── Porchetta tongue landjaeger doner salami pork loin   
│   ├── Ribeye filet mignon capicola   
│   ├── Kevin bacon ham hock meatball swine   
│   ├── How-to recipes   
│   │   ├── Ham hock ground round t-bone corned beef   
│   │   ├── Shoulder frankfurter corned beef alcatra jerky beef   
│   │   ├── Rump beef venison fatback chicken beef ribs brisket   
│   │   ├── Meatball landjaeger short loin   
│   │   ├── Capicola picanha meatloaf beef pork   
│   │   ├── Bacon salami ham frankfurter   
│   │   └── Strip steak rump    
│   ├── Beefy Requirements   
│   │   ├── Picanha tongue biltong brisket short loin   
│   │   ├── Filet mignon kevin spare ribs   
│   │   └── Pancetta shoulder ham   
│   └── Beef sausage   
├── **Bacons**   
│   ├── Bacon salami ham frankfurter   
│   ├── Kevin bacon ham   
│   ├── ham hock pork loin   
│   └── Porchetta tongue   
└── **Animals**   
    └── Bresaola bacon corned beef    

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

# Coming Updates
- Python 3 rewrite
- Documentation
- Dynamic level detection
- Extended API features

