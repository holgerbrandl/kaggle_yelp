
corresponding blog entry https://www.kaggle.com/c/yelp-restaurant-photo-classification/data

## remote training

sync
```bash
scp -r /Users/brandl/projects/dl4j/external/kaggle_yelp talisker:~/projects/deep_learning/dl4j/jkaggle_yelp
rsync -av /Users/brandl/projects/dl4j/external/kaggle_yelp brandl@talisker:/projects/brandl/deep_learning/dl4j/jkaggle_yelp

#https://unix.stackexchange.com/questions/100660/how-to-use-rsync-to-backup-a-directory-without-git-subdirectory
rsync --cvs-exclude -av /Users/brandl/projects/dl4j/external/kaggle_yelp brandl@talisker:/projects/brandl/deep_learning/dl4j/kaggle_yelp

```

remote running
```bash
# ssh talisker

screen -R yelp

cd ~/projects/deep_learning/dl4j/kaggle_yelp

#https://stackoverflow.com/questions/8612614/sbt-selecting-main-class-for-running
sbt "runMain modeling.runPipeline"

mailme "$(pwd): training done"
```

## next step

use cuda drivers instead
https://nd4j.org/gpu_native_backends.html