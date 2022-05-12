# Evil_Twin_Attack

<img src="https://user-images.githubusercontent.com/57721728/168044899-34bc649b-ee79-408b-bdf3-50be1d128521.png" width="600" height="380">

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

<img src="https://user-images.githubusercontent.com/57721728/167908927-99286c05-ff19-4726-9854-0139b912bd44.png" width="400" height="250">

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
![image](https://user-images.githubusercontent.com/57721728/168158706-f183f262-e540-46eb-8d38-5464fbda45af.png)


## second two :
Scan access points in the area and view them,
The attacker then chooses which one he chooses to attack
![image](https://user-images.githubusercontent.com/57721728/168158749-94b81a6d-d641-4755-ad75-1e664976decf.png)


## Step three : 
Displays all connected customers to the same access point he selected in the previous step.
And choosing a client (victim) he wants to attack
![image](https://user-images.githubusercontent.com/57721728/168158813-2489128b-e5ee-46a7-a566-f815ee554fe3.png)


## Step four
The attacker impersonates the original Ap and sends a large amount of Deuthintication facts to disconnect the client from that original Ap to the client (which the attacker wants to attack)
And disconnects it from this approach.
Disable the good twin using SCAPY.
![image](https://user-images.githubusercontent.com/57721728/168158872-5d4334ed-79ec-4985-9170-cc1e906d42e2.png)


## Step Five :
The attacker establishes a fake access point with the same name as the original access point 
(same SSID) The victim's connection to the malicious network

## Step Six:
Uploading the malicious network,
 Activating Portal Captive-
Building a web page, which when the customer tries to enter a particular site he will go straight to the fake site,
where he will have to fill in details about himself to move on.
<img src="https://user-images.githubusercontent.com/57721728/168159121-e6177b07-834e-4f1a-a363-ffa02201920d.png" width="600" height="600">

## Step Seven:
Obtaining the user's information that is the purpose of the attack.
![image](https://user-images.githubusercontent.com/57721728/168159498-2c0c456e-6aa8-4bdf-a1a2-050f2e3b7935.png)


# The defense tool:
<img src="https://criminaldefenseattorneyinchicago.com/wp-content/uploads/2015/04/common-criminal-defenses-chicago-crime-case.jpg" width="400" height="200">

### In this part of the project we tried to think of a defense tool that would allow both customer protection and counterattack.

The defense tool from this is a third party system, which is an attack, and acts in order to protect and thwart the attack.

## The defense:
When an Ap - a new access point is detected, then it is checked by its name, in case it is not in the list of the Ap that are stored on the network, save the information about it and add it to the list.

If it is already on the list,
Then find the Ap that is identical to it in the list.
And check credibility by their mac address, if they are identical then it is secure. If they are different then it is a potential access point to the evil twin attack.
Therefore, since the person in charge of the defense knows who the Ap who was attacked is (because they impersonated her)
Then he connects to it and checks if a large amount of Deathintication facts were sent at a certain time,

If sent then it detects an attack, so it performs an attack thwart:
In order to thwart, he needs to know who the victim is and who the attacker is.
And since Deauthintication facts were sent then there is the address of the source and the address of the destination (valid and valid)
Therefore the head of defense sends such facts of Deauthintication - impersonates the attacker and sends them to the attacker and disconnects the attacker from the fake network, and by sending a large amount of such facts the attacker will be flooded with messages in order to overthrow the network.
We thus thwarted the attack and prevented the attacker from taking personal information of the attacker.

 ### The defense tool is carried out in parallel with the attack:

# Stages of attack:
## step one:
Choose a network interface:

![image](https://user-images.githubusercontent.com/57721728/168117496-84104606-8d80-4f7c-bf37-9a63b534b742.png)

## step two:
 when a new access point is detected then it is checked if it has been previously identified with the same name, then we are shown the name of the address that the attacker (believed) and the fake address that the attacker established
![image](https://user-images.githubusercontent.com/57721728/168107231-70035a2a-adcb-403b-bfa2-e8f971ae6d2f.png)

## step three:
Once the attacker's address and the attacker's address have been presented to the defense officer, 
he must select and enter as input who he wants to defend.

![image](https://user-images.githubusercontent.com/57721728/168117835-5850b16d-d913-4b30-9e07-7ea716e2976f.png)

## step four:
At this point it checks whether the selected Ap is under evil twin attack
match by checking the sending of a large amount of Deauthintication facts at a certain time.

![image](https://user-images.githubusercontent.com/57721728/168120940-8a1e90fe-e03d-4bd8-be45-7c4fc6da2de2.png)
![image](https://user-images.githubusercontent.com/57721728/168121096-745c25df-581f-445f-8d69-4c62f3b94471.png)


## step five: 
Prevention of the attack:
 The protection officer saves the victim's information contained in the disconnection packages, 
 and sends through the attacker Deauthintication facts
Attack and disconnect him thus thwarting the attack, and in addition when he sends the facts he sends full ones so that it will drop him the net.

### The purpose for which Moses' defense was intended was completed

<img src="https://user-images.githubusercontent.com/57721728/168120300-5736c7bf-c390-4896-a005-304cda629128.png" width="400" height="200">
