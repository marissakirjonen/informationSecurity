## All Homework Reports!

1. [h1-FirstSteps](https://github.com/marissakirjonen/informationSecurity/blob/main/h1-FirstSteps.md)
2. [h2-SpiderWebs](https://github.com/marissakirjonen/informationSecurity/blob/main/h2-SpiderWebs.md)
3. [h3-ShouldTeroWearAaHelmet](https://github.com/marissakirjonen/informationSecurity/blob/main/h3-ShouldTeroWearaHelmet.md)
4. [h4-ETAOIN](https://github.com/marissakirjonen/informationSecurity/blob/main/h4-ETAOIN.md)
5. [h5-September2023!](https://github.com/marissakirjonen/informationSecurity/blob/main/h5-September2023!.md)
6. [h6-A.Nyomous](https://github.com/marissakirjonen/informationSecurity/blob/main/h6-A.Nynomous.md)


## Install Firewall

First we start off with updating any packages and their dependencies with the command:

    sudo apt-get update

![Näyttökuva 2023-10-06 212700](https://github.com/marissakirjonen/informationSecurity/assets/142782994/56566062-975b-4370-8eaa-3c05034a90cd)

Now we can install the ufw ("Uncomplicated Firewall") package using this command:  

    sudo apt-get install ufw

![Näyttökuva 2023-10-06 212711](https://github.com/marissakirjonen/informationSecurity/assets/142782994/9d3f62f8-3155-481c-8b9a-876e0c75b217)

Next we can allow specific ports to be open using the following commands: 

    sudo ufw allow 22/tcp

This command is for allowing incoming connections to my system on the port 22, which is the default port for Secure Shell (SSH).

![sudo22](https://github.com/marissakirjonen/informationSecurity/assets/142782994/88221c53-0ad7-4155-806b-64760138fb69)


One extra note: if you have to delete a port, for example if you added the wrong port number, this can be done with the following commands: 

    sudo ufw status numbered
    sudo ufw delete (the number you want to delete)

![Näyttökuva 2023-10-07 212909](https://github.com/marissakirjonen/informationSecurity/assets/142782994/7d930bd1-1d36-46b0-a17a-5754ebc25082)

We can now check the status of the ufw and see if the deletion worked with this command:

    sudo ufw status

![Näyttökuva 2023-10-07 213201](https://github.com/marissakirjonen/informationSecurity/assets/142782994/847fff02-d630-4ef8-9d97-02f4796c185e)

After this we can enable the firewall, which now the rules we placed previously will take effect, using the command: 

    sudo ufw enable

![sudo23](https://github.com/marissakirjonen/informationSecurity/assets/142782994/fb02adb4-d5db-4579-8e64-b0c028659a9b)


## Ssherver. Install OpenSSH server and connect to it.

Now we will install Open Secure SHell (OpenSSH), which allows for remote control access to a computer using encryption. 

To start off, we will use this command to install ssh and the next command to start: 

    sudo apt-get install ssh
    sudo systemctl start ssh

![Näyttökuva 2023-10-07 220812](https://github.com/marissakirjonen/informationSecurity/assets/142782994/e4b79396-8086-4794-b87f-9354286fe96d)


It's good to note that the command sudo systemctl start ssh doesn't display anything to the terminal. If you would like to see if the command worked, we can use this command to check if it's running: 


    sudo systemctl status ssh


![Näyttökuva 2023-10-07 221245](https://github.com/marissakirjonen/informationSecurity/assets/142782994/a5368d11-7853-48b9-8f67-be5fdc3c45ff)


Next, let's go ahead add a new user for ssh access!

First let's check who i'm currently logged in as with the following command: 

    whoami

![Näyttökuva 2023-10-07 221835](https://github.com/marissakirjonen/informationSecurity/assets/142782994/86fb7007-d161-4d70-a49f-6370202a6204)

To add new user named mtest, use the following command: 

    sudo adduser mtest

Remember to add a good password!!

![Näyttökuva 2023-10-07 222635](https://github.com/marissakirjonen/informationSecurity/assets/142782994/b560d48b-3881-4550-93e9-e289dcb0dd61)

Now we can switch to the mtest user with: 

    su mtest

- su: "substitute user"

![Näyttökuva 2023-10-07 222847](https://github.com/marissakirjonen/informationSecurity/assets/142782994/b1ce5d7b-1fe6-468a-8456-41ea8b74272a)

Next, we will generate authentication keys for SSH with the following command: 

    ssh-keygen

- This generates a pair of keys: private key and public key.
- We will also make this without a passphrase (which secures private keys).


![Näyttökuva 2023-10-07 223606](https://github.com/marissakirjonen/informationSecurity/assets/142782994/eecb8fde-2dc4-4e80-8704-015fb49e7df8)


Next, we will copy the public SSh key to the remote computer, which will set up passwordless login! Use the command: 

    ssh-copy-id

![Näyttökuva 2023-10-07 224402](https://github.com/marissakirjonen/informationSecurity/assets/142782994/3773d734-1ed6-4757-b7b8-a3d4404375e5)


Let's test!

![Näyttökuva 2023-10-07 224835](https://github.com/marissakirjonen/informationSecurity/assets/142782994/be110e6e-fcad-41a5-8084-4fd94081762e)




