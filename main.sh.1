#!/bin/bash

# help message
if [ "$1" = "-h" ] || [ "$1" = "--help" ]; then
	echo "bootstrap github deploy json file"
	echo "--revert     revert back to old json file"
	echo "--help       print this message"
	exit 0
fi

user="$1"
reponame="$2"
cp package.json /tmp/package.json.old 2>&1 >/dev/null

function printErr(){
	echo -e "\e[32m[ERR] ${1}\e[0m\n"
}

function printPass ()
{
	echo -e "\e[34m>> ${1}\e[0m\n"
}

echo -e "\e[34m >>> github pages bootstrap <<< \e[0m\n"

# Checking if files exist
jsonfile="package.json"
temp=/tmp/package.json.old

[ -f $jsonfile ] && cp $jsonfile $temp || {
	printErr "package.json not found"
	exit 1
}

# parsing user input 
[ ! -z $user ] && [ -z "$reponame" ] && [ "$user" = "--revert" ] && {
	if [ -f /tmp/package.json.old ]; then
		cp /tmp/package.json.old ./package.json 2>/dev/null
		printPass "revert done"
		exit 0
	fi
	printErr "no backup file found"
	exit 0
}

[ -z "$user" ] || [ -z "$reponame" ] && {
	printErr "run file with username and reponame as argument"
	printf "\t%s <username> <repo name>\n" "$0"
	exit 1
}

function installpackage() {
	npm list | grep "gh-pages@.*" >/dev/null 2>/dev/null && printPass "gh-pages found" || {
		npm install gh-pages
		printPass "\ngh-pages installed"
	}
}


installpackage

# asking for cross checking
echo -e "\e[34m >>> data <<< \e[0m"
echo "gitHub Username:  $user"
echo "gitHub repo:      $reponame"
echo "proceed?[Y,n]"
read ans

if [ "$ans" = "n" ] || [ "$ans" = "N" ]; then
	echo -e "exiting..."
	exit 0
fi

# edit the files
[ !  -f /bin/sed ] && { 
    printErr "sed not found, This script only works on linux"
    exit 1
}
# apply first changes to package.json
sed "s|\"name\":|\"homepage\": \"https://${user}.github.io/${reponame}\",\"name\":|g" -i $jsonfile
sed "s|\"start\":|\"predeploy\": \"npm run build\",\"deploy\": \"gh-pages -d build\",\"start\":|g" -i $jsonfile
sed  "s|\"scripts\":[, ]{| \"scripts\": { \"predeploy\": \"npm run build\",\"deploy\": \"gh-pages -d build\",|g" -i $jsonfile
printPass "package.json"
cat $jsonfile
