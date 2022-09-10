# Split a large CSV file and add headers to each file

## Step One: Split file

```
$ split -l 5000 users.csv ./split-files 
```

> 5000 is the number of lines you want for each file.)

## Step two: Appending ‘.csv' to each file

```
$ cd ./split-files
$ for f in *; do echo mv "$f" "$f.csv"; done 
```

## Step three: Adding header to each file 

```
for i in *.csv; do sed -i '' '1i\  
First column name, Second column name, etc, etc  
' $i; done 
```
