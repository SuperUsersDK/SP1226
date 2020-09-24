# Exercise 9.1

```bash
echo Filenames with 3 characters in length:
ls -ld ???
echo

echo Filenames with 4 characters in length:
ls -ld ???
echo

echo Filenames with 5 characters in length:
ls -ld ???
echo

echo Report made by $LOGNAME - $(date +%F)
```

# Exercise 9.2
```
cd bestilling
NUMBER_OF_FILES=$(ls |wc -l)

if [ $NUMBER_OF_FILES -ne 1 ]
then
  echo The number of files is not correct.
  exit 1
fi
echo The number of files is correct

if ls [0-9][a-z]
then
  echo Correct filename
else
  echo Incorrect filename
  exit 2
fi

if cp * ../Kap.5/
then
  echo Copying the file without problems
else
  echo Copy failed
  exit 4
fi

WORD_ON_FIRST_LINE="$(head -1 *)"
if [ "$WORD_ON_FIRST_LINE" = "bog" ]
then
  echo Correct word on first line
else
  echo Not correct word on first line
  exit 3
fi
```

# Exercise 9.3
```bash

cd Kap.5/dir-a/
for FILE_IN_A in *
do
  if [ -f ../dir-b/$FILE_IN_A ]
  then
    echo File $FILE_IN_A already exists in dir-b/
  else
    cp $FILE_IN_A ../dir-b/
  fi
done

cat ../dir-b/* > ../Kontrolfil
```

# Exercise 9.7
```bash
if [ "$1" = "Los Angeles" -o "$1" = "Store Heddinge" ]
then
  exit 0
fi
echo "Not correct city name"
exit 1
```

# Exercise 9.8
```bash
INNER=A
MIDDLE=INNER
OUTER=MIDDLE
CRAZY=OUTER

echo $INNER
eval echo \$$MIDDLE
eval eval echo \\$\$$OUTER
eval eval eval echo \\\\\$\\\$\$$CRAZY
```


