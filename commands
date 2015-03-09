Stop any process running on port 53:
sudo kill `sudo lsof -t -i:53`

see whats happening on ports:
netstat -anp

start my hotspot
ap-hotspot start/stop


Take Mysql dump:
mysqldump -u root -p123456 indus_19533 > 19533.sql

Restore:
mysql -u root -p123456 indus_19533 < indus_19533.sql

Take compressed Mysql dump:
mysqldump -u root -p123456 indus_19533 | gzip > 19533.sql.gz

Restore:
gunzip < output.sql.gz | mysql -u <username> -p<password> <database>

#Add all items which posses status [AU = unmerged, Added by us].
#This command can be easily modified to remove or add files to git based on staus.
git status --porcelain | awk '{if($1=="AU") print $2}'| xargs git add

#Remove all items which posses status [UA = unmerged, Added by them OR DD = both deleted].
##NOTE: untested
git status --porcelain | awk '{if(($1=="UA")||($1=="DD")) print $2}'| xargs git rm

#A conbination of above two commands to:
#Add all items which posses status [AU = unmerged, Added by us].
#Remove all items which posses status [UA = unmerged, Added by them OR DD = both deleted]
#faulty
git status --porcelain | awk '{if(($1=="UA")||($1=="DD")){print "git","rm",$2} else if($1=="AU"){print "git","add",$2}}'| xargs --interactive




