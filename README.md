# switchapp
This script file is to be used with <b>Touchegg</b> to allow switching between opening application windows in the current desktop using a swipe guesture.<br/>

<img src="https://github.com/vathanak-mao/switchapp/blob/main/.github/switchapp.gif"/>

## How-to
Here is how to configure 4-finger swipe down for switching to another app window:
1. Install `xdotool` and `wmctrl` if not exist
<pre>
sudo apt-get update
sudo apt-get install xdotool wmctrl -y`
</pre>
2. Install `touchegg` and make sure it's up and running (more details can be found [here](https://github.com/JoseExposito/touchegg))
3. Download and copy the `switchapp` script to `/usr/bin`
4. Open this file `~/.config/touchegg/touchegg.conf` and add the following lines inside the `<application>` tag:
<pre>
&lt;gesture type=&quot;SWIPE&quot; fingers=&quot;4&quot; direction=&quot;DOWN&quot;&gt;
    &lt;action type=&quot;RUN_COMMAND&quot;&gt;
	&lt;repeat&gt;false&lt;/repeat&gt;
	&lt;command&gt;switchapp&lt;/command&gt;
	&lt;on&gt;begin&lt;/on&gt;
    &lt;/action&gt;
&lt;/gesture&gt;
</pre>
5. Press Alt+F2 then type 'r' without quotes to restart GNOME Shell; if it doesn't work, reboot.

## Options
### reverse 
It switches to previously openning application window. <br/></br>
Example:
<pre>
&lt;gesture type=&quot;SWIPE&quot; fingers=&quot;4&quot; direction=&quot;UP&quot;&gt;
    &lt;action type=&quot;RUN_COMMAND&quot;&gt;
	&lt;repeat&gt;false&lt;/repeat&gt;
	&lt;command&gt;switchapp reverse&lt;/command&gt;
	&lt;on&gt;begin&lt;/on&gt;
    &lt;/action&gt;
&lt;/gesture&gt;
</pre>
