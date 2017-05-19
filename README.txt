# oereb

1.Creation of base directory for the project: oereb
cd oereb

2. prepare it for git
git init

3. Install the virtual environnement (supposed you already have python installed)
virtualenv --setuptools --no-site-packages .build/venv

4. Install a basic Pyramid component
.build\venv\Scripts\pip install pyramid==1.7.4

5. get one level up to create the empty project
cd ..
oereb\.build\venv\Scripts\pcreate.exe -s alchemy oereb

6. Delete unused files for this project:
 cd oereb
 
- .coveragerc
- CHANGES.txt
- MANIFEST.in
- pytest.ini

7. Maybe create an github project with this base structure and push it
but first create a .gitignore file with at least
*.pyc
/.build
as content - other files will follow...
git add .gitignore
git commit -m "added .gitignore"

then create your git repository and add is as remote to the local directory:
git remote add upstream https://github.com/youraccount/oereb.git

8. collect complementary files created on github such as the README.md
git fetch upstream
git merge upstream/master

9. Add your local files and push them to the repository to get an clean initial version
git add -A
git commit -m "commit message"
git push upstream master

On windows there's a problem with the shapely dependencies, so before installing
all the other dependencies, one should manually install shapely and psycopg2 wheels:
.build\venv\Scripts\pip install wheel [path to psycopg2-2.5.5-cp27-none-win32.whl or other version]