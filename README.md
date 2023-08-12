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

```bash
pytest -v
```
above command generates pycache directory