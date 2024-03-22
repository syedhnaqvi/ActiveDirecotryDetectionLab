# Active Directory Detection Lab

## Objective
The purpose of generate telemetry data and see detctions in action .

### Skills Learned

- Kali Commands as Pen testing .
- Generating Telemtry data for detections ( Bruteforcing attack)
- View Telemetry in splunk 
- Atomic Red Team Installtion and setup - Run Atomic Tests 


### Tools Used

- Splunk
- Kali
- Crowbar for bruteforcing attacks
- ART

## Ref Diagram
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/12def3c0-0854-48cd-9903-36f31bf05156)


### References 
<a href= "https://youtu.be/orq-OPIdV9M">Video Tutorial</a>

### STEP -1
Setup & assign static IP to kali 192.168.10.250 as per diagram
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/c3d91063-eeb8-4cd7-9523-97c2ba02b386)

### Step -2
Check Connectivity using ping commands : ping google.com and ping 192.168.10.1o ( Our Splunk Sevrer) if you get reply all good !

### Step -3
Update and Upgrade Kali Repo's using commands sudo apt-get update && sudo pat-get upgrade -y

### Step -4
Create New Directory using command mkdir ad-project in Desktop Folder
### Step -5
Install tool crowbar on Desktop command using sudo apt-get install -y crowbar
This package contains Crowbar (formally known as Levye). It is a brute forcing tool that can be used during penetration tests
<a href="https://www.kali.org/tools/crowbar/">Read More</a>
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/15736ecc-376e-481d-9952-48d153d41fe1)

### Step -6
Using rockyou wordlist location /usr/sahre/wordlists
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/22d93cbd-aa31-491f-9154-b9ddb15ddcaa)

Unzip file using gunzip command : sudo gunzip rockyou.txt.gz
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/ee9f344a-0591-422b-b7ff-34edf06499fc)

Copy file rockyou.txt to /Desktop/ad-project direcotry cp rockyoiu.txt ~/Desktop/ad-project
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/416e072c-6f91-4e99-8c3f-fbbfdcce6ee8)

Use only first 20 lines instead of using whole file that is huge in size use command head -n 20 > password.txt ( output to txt file)
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/c8b417a5-9a47-4971-888a-605b13c140e7)

![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/72b40eaa-3e48-4f59-bae5-55f59dfd6335)

Add a more password to file using sudo nano passwords.txt
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/235c9cdc-eb2c-4af3-9c53-22543ba52dd4)
Save CTRL+X Then Y Press Enter.

### Step -7
<b>Enable RDP in Win10 Target Machine</b>
Search PC then click on Properties
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/e48af4d1-fbff-4915-9ea1-9515756198b6)

![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/aad6bcf8-c9ca-4949-bfab-0e1a468a3256)

![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/d4c94166-eedb-4e2a-b707-6854e04448fa)

![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/8012a145-8a1c-4cec-9284-20d52365e3e0)

![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/e6394611-8691-43d4-840e-959c30f79c2c)

User Click ADD
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/abb78167-0795-4233-a6c1-db2ca3491006)

Add user jenny smith and terry smith we created earlier . After typing user click check names
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/51ac41cc-14ce-40f9-9e0e-9fd11bbf2360)

### Step -8
Use Crowbar for bruteforcing attack
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/e8f3e408-73ff-4734-8625-10e79ffdfdbd)
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/b89a1aba-304f-4c8f-aebc-e0075eefccc1)

### Step -9
Check in SPlunk What telemtry generated from the above bruteforcing activity.
Check for index=endpoint tsmith user we used for attack then event id 4625 failed sttempts .
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/2a92062e-c447-4eb4-80ad-986a9e845056)

Note : Check event timing happening rapidly clear indication of brute force attempts then check event id 4624 successful login will show 1 event.
![image](https://github.com/syedhnaqvi/ActiveDirecotryDetectionLab/assets/39069507/e6081a20-61ae-47f6-9600-ea21f7b1eb03)







