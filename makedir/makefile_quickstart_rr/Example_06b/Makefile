f = out_file.txt
g = match.txt

default: match
	echo "(Info) Done"

write: 
	if [ -e $f ] ; then echo "(Info) Deleting existing version of $f" ; rm $f ; fi
	echo "(Info) Twinkle, twinkle, little star" > $f
	echo "(Info) How I wonder what you are " >> $f
	echo "(Info) Up above the world so high" >> $f
	echo "(Info) Like a diamond in the sky"  >> $f
	echo "(Info) Twinkle, twinkle little star" >> $f
	echo "(Info) How I wonder what you are" >> $f

match: write
	if [ -e $g ] ; then echo "(Info) Deleting existing version of $g" ; rm $g ; fi
	grep -n "in" $f > $g

