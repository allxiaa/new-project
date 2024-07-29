How to do:
mkdir new-project
cd new-project
git init
echo -e 'Hello' > README.md
h1=$(git hash-object -w README.md)
git update-index --add --cacheinfo 100644 $h1 README.md
t1=$(git write-tree)
c1=$(echo -n 'init'|git commit-tree $t1)
git update-ref refs/heads/main $c1
git checkout -b developer
git commit -m "add branch development"