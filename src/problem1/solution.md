
## Problem 1
Run below cli:
```sh
sudo apt install jq -y &&  while read -r line; do ID=$(echo $line | jq -r 'select(.symbol == "TSLA") | .order_id'); if [[ $ID != "" ]]; then curl https://example.com/api/$ID >> ./output.txt; fi done < transaction-log.txt
```