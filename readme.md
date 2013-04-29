# dummy-smtp

Catch messages sent via SMTP

For use from within a vagrant VM


## Requirements

A [Vagrant](http://www.vagrantup.com) VM with Java installed (JDK 1.4 or newer)

Uses DevNullSmtp.jar.jar, see also [What is DevNull SMTP](http://www.aboutmyip.com/AboutMyXApp/DevNullSmtp.jsp)


## License

MIT License for this repository, except the file DevNullSmtp.jar.

DevNullSmtp.jar is available for free download at http://www.aboutmyip.com/AboutMyXApp/DevNullSmtp.jsp, I could not find any license information, I've contacted synametrics.com



## Installation

- Clone / Copy the repository into the Vagrant project root folder
- Make sure the folder dummy-smtp/mails is writeable from within the VM


## Usage 

From within the VM 

```
sudo java -jar /vagrant/dummy-smtp/DevNullSmtp.jar -console -s /vagrant/dummy-smtp/mails -p 1025
```

In the above case the application is set up to send mail via SMTP using port 1025

## All Options


**-console**	

If specified, runs the server in console mode. For example:

```
java -jar DevNullSmtp.jar -console
```

This command will run the server in console mode on port 25 and will accept emails from every domain. Incoming emails will be destroyed.


**-p**

Specifies a port number. For example: 

```
java -jar DevNullSmtp.jar -p 2500 -console
```

This command will run the server in console mode on port 2500 and will accept emails from every domain. Incoming emails will be destroyed.

**-s**

Specifies the path where emails are stored. This must refer to a valid path on your machine. For example: 

```
java -jar DevNullSmtp.jar -p 2500 -console -s c:\temp\emails
```

This command will run the server in console mode on port 2500 and will accept emails from every domain. Incoming emails will be saved in c:\temp\emails folder.

**-d**

Specifies acceptable domain names. For example: 

```
java -jar DevNullSmtp.jar -console -d firstDomain.com,secondDomain.com 
```

This command will run the server in console mode on port 25 and will accept emails from firstDomain.com and secondDomain.com. Incoming emails will be destroyed.

**-h**

Displays the USAGE screen on the window and exists.