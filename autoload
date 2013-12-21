#!/bin/bash
catiplist=`dirname $0`"/catiplist"
iplist=`dirname $0`"/IPLIST"

if [ $# != 1 ]
then
    awk -f $catiplist $iplist loadiprank=$1 
    exit;
fi

if  echo $1 | grep -q '^[0-9]\+$'
then
    ip=`awk -f $catiplist $iplist loadiprank=$1 | cut -d " " -f 1`
    user=`awk -f $catiplist $iplist loadiprank=$1 | cut -d " " -f 2`
    passwd=`awk -f $catiplist $iplist loadiprank=$1 | cut -d " " -f 3`
    sshpass -p "${passwd}" ssh "${user}"@"${ip}"
    exit;
else
    awk -f $catiplist $iplist loadiprank=$1 
    exit;
fi
