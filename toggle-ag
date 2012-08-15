#!/system/bin/sh
#This script was developed for use with the Acer Iconia A100
#Android tablet while using the Autogroup Custom Kernel that I released.
#However it should be compatible with any  other android device or
#Linux based system that has SCHED_AUTOGROUP enabled.
#The sole purpose of this script is to simply check
#the status of the Autogroup Scheduler and to give the user
#control over whether it is running or not as some users may
#prefer the tradtional CFS (Completely Fair Scheduler) which is
#what the scheduler will fallback to when Autogroup is disabled 

#Use 'toggle-ag help' to display the proper usage
#For easiest use, make three widgets with Script Manager, 
#and assign the following commands to the widgets:
#	toggle-ag status
#	toggle-ag start
#	toggle-ag stop
#Put the widgets on your home screen and have easy 1 click control
#over the Autogroup Scheduler

#**Please note that toggling back and forth the scheduler will
#produce undesired effects, as it takes the system a few minutes
#to switch the process scheduler each time effectively. Imagine 
#all processes that run in the backround are rearranged each time
#you switch the process scheduler. In other words you shouldn't 
#toggle back and forth to make comparisons as they WILL NOT be 
#effective immediately!!

#This script is free as in FREE and can be distributed in any way
#shape or form, all I ask is that you give credit where credit is
#due when altering this script or distributing it.

#Written by Godmachine81 <Lance Poore linuxsociety@gmail.com>
#Aug 12, 2012


file=/proc/sys/kernel/sched_autogroup_enabled
state="`cat $file`"
case $1 in
on)
	state="`cat $file`"
	if [ "$state" == 1 ];then
		echo "Autogroup is already Enabled!!"
		exit 1
	fi

	echo "Enabling Autogroup"
	echo "1" >> $file
	state="`cat $file`"
	if [ "$state" == 1 ]; then
		echo "Successfully enabled Autogroup"
		exit 0
	else
		echo "File says: $state should say 1"
		echo "Something went wrong, are you root?"
		exit 1
	fi
;;

off)
		state="`cat $file`"
	if [ $state == 0 ];then
		echo " Autogroup is already Disabled!"
		exit 1
	fi
		echo "Disabling Autogroup"
		echo "0">> $file 
		state="`cat $file`"
	if [ "$state" == 0 ]; then
		echo "Successfully disabled Autogroup"
		exit 0
	else
		echo "File says $state, should say 0"
		echo "Something went wrong, are you Root?"
		exit 1
	fi

;;
status)
	state="`cat $file`"
	if [ "$state" == "1" ]; then
			echo "AutoGroup is currently enabled"
		else 
			echo "AutoGroup is currently disabled"
	fi
;;

help)
	echo "This script was developed to simply enable / disable SCHED_AUTOGROUP"
	echo "to separate the need for two different compiled kernels"
	echo 
	echo "Usage:"
	printf " toggle-ag on      Turns Autogroup Scheduling on\n toggle-ag off     Turns Autogroup Scheduling off\n toggle-ag status  Displays the current status  of Autogroup\n toggle-ag help    Display usage (this)\n"
;;

*)
	echo "Error: the correct usage is:  toggle-ag on|off|status|help"
	exit 1
;;
esac
