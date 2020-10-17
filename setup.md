setup.sh

	#!/bin/bash

	PATH_TO_SCRIPT="/root/package.sh"

	UserName="Your system's normal username"
	Password='Password'

	hosts="/root/list"

	for i in $(cat $hosts)
	do

	sudo -S sshpass -p $Password ssh -o stricthostkeychecking=no $UserName@$i 'sudo -s ' < $PATH_TO_SCRIPT
	echo $i success

	done