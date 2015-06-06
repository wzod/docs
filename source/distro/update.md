Starting with the [v6 release](https://zeltser.com/remnux-v6-release-for-malware-analysis/), the REMnux distro allows its users to conveniently update REMnux software without having to install the updated REMnux system from scratch. To do this, first connect your REMnux system to the Internet. Then run the following command:

    update-remnux

The script takes 5-10 minutes to run, depending on the speed of your Internet connection and the power of your host. It will update the packages intalled as part of the REMnux environment and add any tools incorporated into the distro since your previous update.

If you've added any tools to your environment using "apt-get" beyond those that came with REMnux, you can run the following commands after "update-remnux":

    sudo apt-get update
    sudo apt-get upgrade

Consider following REMnux accounts on [Twitter](https://twitter.com/REMnux), [Facebook](https://www.facebook.com/REMnux) and [Google Plus](https://plus.google.com/+REMnuxOrg) to receive notifications when its malware analysis packages are updated or when new ones are added to the toolkit.
