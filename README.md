# Evil_Twin_Attack

<img src="https://linuxsecurityblog.files.wordpress.com/2018/10/evtwat.jpg" width="600" height="380">

## The purpose of this project was:
### To build an evil twin attack in addition to a defense tool which can prevent and thwart the attack.
We did it in the Communication Network Protection course,

We will first explain what an evil twin attack is and the steps have come how we performed and finally we will explain how we can thwart and defend against it.

## What is an evil twin attack and what is it based on?
 we use a Fiat-based Plath network which allows you to connect between different networks:
 laptops, smart phones, etc.
 in another wired or provided network using a connection medium.
And it works by point-access which serves as the transition point between the networks.
The role of Point-Access is to manage the wireless network by the wireless medium between consumers and the connection between the consumer and the network.
For the purpose of identifying the wireless network, each Point-Access has a network name that identifies it, known as the SSID - short for IDentifier Set Service.))

- This attack allows the endpoint to be deceived by adding a point-of-access (SSID) identical to the real point-access 
and will cause the endpoint to connect to the additional point-access instead of the original point-access.
The other access is called "Point-Access Rogue."
 Point-Access will publish the network name (SSID) by sending an appropriate Beacon message,
when the message is sent as a Broadcast due to the characteristics of the wireless medium.

- This means that everyone in the Point-Access environment is aware of the existence of the wireless network.
The endpoint will try to connect automatically to the Point-Access that publishes a particular SSID if the user previously connected through the endpoint to the same network with the same SSID) then whenever the endpoint detects that there is a Fi-Wi network in the area with the same SSID, 
it will try to connect The security mechanism that has been set up for this network.
And from the moment the attacker is under the fake access point the attacker can sniff information and passwords of the attacker and use it.

<img src="https://user-images.githubusercontent.com/57721728/167908927-99286c05-ff19-4726-9854-0139b912bd44.png" width="300" height="200">

### - Stages of execution of the "Evil twin attack":
 We will now detail the stages of the attack we carried out
We implemented a system that allows an attacker to enter the input he chooses at each stage of the attack:
1. Scans the area, looking for wifi access
2. Choose which wifi we want to attack
3. Sending examination requests / death packages that cause the victim to be disconnected
4. Upload a fake AP with the same SSID
5. Customers will connect to our fake AP
6. The victim is directed to the site where he needs to fill in his details (the details are kept with the attacker)

## The attack is done as follows (as shown)
<img src="https://user-images.githubusercontent.com/57721728/168020104-62d0809e-5e67-4b81-a707-5cbeb20853f8.png" width="600" height="380">

## In order to illustrate the execution of the attack, pictures and explanations are attached after each stage

## Step one :
Scanning the network cards in the area and entering the user on which network he wants to carry out the attack

## second two :
Scan access points in the area and view them,
The attacker then chooses which one he chooses to attack

## Step three : 
Displays all connected customers to the same access point he selected in the previous step.
And choosing a client (victim) he wants to attack

## Step four
The attacker impersonates the original Ap and sends a large amount of Deuthintication facts to disconnect the client from that original Ap to the client (which the attacker wants to attack)
And disconnects it from this approach.
Disable the good twin using SCAPY.

## Step Five :
The attacker establishes a fake access point with the same name as the original access point 
(same SSID) The victim's connection to the malicious network

## Step Six:
Uploading the malicious network,
 Activating Portal Captive-
Building a web page, which when the customer tries to enter a particular site he will go straight to the fake site,
where he will have to fill in details about himself to move on.

## Step Seven:
Obtaining the user's information that is the purpose of the attack.

# The defense tool:
<img src="https://criminaldefenseattorneyinchicago.com/wp-content/uploads/2015/04/common-criminal-defenses-chicago-crime-case.jpg" width="300" height="200">
### In this part of the project we tried to think of a defense tool that would allow both customer protection and counterattack.

The defense tool is carried out in parallel with the attack:


