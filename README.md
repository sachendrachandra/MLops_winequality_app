conda environment creation

``` bash
conda create -n wineq python=3.7 -y
```

activate environment

```bash
conda activate wineq
```

install requirements.txt

```bash
pip install -r requirements.txt
```

download wine quality dataset from kaggle and put it in "data-given"(it acts ac external source of data) directory
https://www.kaggle.com/datasets/yasserh/wine-quality-dataset?resource=download

```bash
git init
```

install dvc(data version control)

```bash
brew install dvc
```

```bash
dvc init

dvc add data_given/winequality.csv

git add .
git commit -m "first commit"
git remote add origin https://github.com/sachendrachandra/MLops_winequality_app.git
git push -u origin main
```

update dvc.yaml file
```bash
dvc repro
```

check metrics
```bash
dvc metrics show
```

check metrics history 
```bash
dvc metrics diff
```

what is tox ?
https://tox.wiki/en/4.7.0/

create test methods in tests/test_config.py. Make sure the module name always starts with "test" keyword

first run below commands

```bash
tox
```

incase you make changes in requirements,txt file and what to recreate tox environmenet, run below command

```bash
tox -r
```

```bash
pytest -v
```
above command generates pycache directory in tests folder

You can set up setup.py file to package your application. setup.py files looks for __init__.py files in all folder and treat as python package and create a package. After creating setup.py file you need to run below command to create a package folder.

```bash
pip install -e .
```
If you run "pip freeze" command you will see "src" in the list of packages. It means your appplication is converted into a package.

now to create a tar file you need to execute below command.

```bash
python setup.py sdist bdist_wheel
```
You will see a "dist" folder containing a tar file which can be shared to run your application.


NOTE: In pytest.py file you can specify any custom test. However each custom function must start with 'test' keyword or else while executing "pytest -v" command won't run fucniton which don't start with 'test' keyword.

