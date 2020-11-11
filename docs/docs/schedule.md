# Schedule

The **Schedule** is used for the automatic refreshes of all the data imports done in the SkyPoint Customer Data Platform (CDP). This can also help in running specific jobs on a regular basis as per requirements. The Schedule ensures all the data in the CDM is upto date.

## Steps to Set-Up the Schedule

1. Go to **Settings** > **Platform** and **Click** on **Schedule** Tab.
1. The default state of the schedule is **OFF**. To enable **Click** on the toggle at the top of the screen.
1. Choose between **Weekly** or **Daily** refresh. If **Weekly** is selected then select one or more days on which you want to run the refresh.

1. Set your **Time zone**, then use the **Time** dropdown to set your refresh timing. If multiple refresh is required in a signle day, **Click** on **Add another time**
1. Next, we select the type of Stitch flow based on user's requirements. Select any of the flow **(Rule Flow or ML Flow)** that the user wants to gets processed in this schedule.
1. **Click** on **Save** to apply the changes.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/Schedule.png?raw=true)