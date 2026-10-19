# basic_bish_scripts
Basic_Bish_Scripts


## SIMPLE LINUX RENAME SCRIPTS


### RENAME WITH A TIMESTAMP
prefix=$(date +%Y%m%d)  # Store timestamp in a variable
for file in *; do 
  if [ -f "$file" ]; then 
    mv -- "$file" "${prefix}_$file" 
  fi 
done


### RENAME WITH A COUNTER 

#### ---  Change file extension ---  Remove $file if you want a clean filename with no remnant   --- 

counter=1
for file in *.jpg; do 
  mv -- "$file" "image_$(printf "%03d" $counter)_$file"  # %03d = 3-digit number (001, 002...)
  ((counter++))  # Increment counter
done
