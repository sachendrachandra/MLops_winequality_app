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

git init

install dvc(data version control)

```bash
brew install dvc
```

dvc init

dvc add data_given/winequality.csv

git add .
git commit -m "first commit"



