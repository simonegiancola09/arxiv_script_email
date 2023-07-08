**arxiv.sh**:  automated daily query for new arXiv.org articles in select subjects via RSS

I schedule the script to run daily and email the results to myself, which I read in Claws Mail (screenshot attached; links open in web browser).

```
# /etc/crontab
# "At 6:00 am daily" [http://crontab.guru/]:
0    6    *    *    *    victoria    nice -n 19    /mnt/Vancouver/programming/scripts/arxiv.sh
```

Due to the way arXiv.org presents the data, some older results are retained on each day but they are clearly delineated in the script output and can be ignored (scroll past them) or used for reference to older results.

Commands to make crontab work
=====
Call ```crontab -e ```, an editor opens. Need to add commands such as:
```
CRON_TZ=UTC
min  hour  day_of_month  month  day_of_week  simone nice -n 19 path/to/file.sh
```
where the first one makes sure that the server runs in UTC time. 
Example
```
CRON_TZ=UTC
0 9 * * * simone nice -n 19 Desktop/filename.sh
```
Runs at 9:00 AM UTC the script. 

Obviously, it needs to be saved locally. 
