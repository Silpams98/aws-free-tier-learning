
If you have sudo permissions, you can install the AWS CLI for all users on the computer. We provide the steps in one easy to copy and paste group. See the descriptions of each line in the following steps.


$ curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
$ sudo installer -pkg AWSCLIV2.pkg -target /
Guided installation instructions
Download the file using the curl command. The -o option specifies the file name that the downloaded package is written to. In this example, the file is written to AWSCLIV2.pkg in the current folder.


$ curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
Run the standard macOS installer program, specifying the downloaded .pkg file as the source. Use the -pkg parameter to specify the name of the package to install, and the -target / parameter for which drive to install the package to. The files are installed to /usr/local/aws-cli, and a symlink is automatically created in /usr/local/bin. You must include sudo on the command to grant write permissions to those folders.


$ sudo installer -pkg ./AWSCLIV2.pkg -target /
After installation is complete, debug logs are written to /var/log/install.log.

To verify that the shell can find and run the aws command in your $PATH, use the following commands.


$ which aws
/usr/local/bin/aws 
$ aws --version
aws-cli/2.27.41 Python/3.11.6 Darwin/23.3.0
If the aws command cannot be found, you might need to restart your terminal or follow the troubleshooting in Troubleshooting errors for the AWS CLI.


Last login: Wed Jul 29 09:53:56 on console
Apple@MacBook-Pro ~ % curl "https://awscli.amazonaws.com/AWSCLIV2..." -o "AWSCLIV2.pkg"

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  6110  100  6110    0     0   7018      0 --:--:-- --:--:-- --:--:--  7014
Apple@MacBook-Pro ~ % sudo installer -pkg ./AWSCLIV2.pkg -target /

Password:
installer: Error - the package path specified was invalid: './AWSCLIV2.pkg'.
Apple@MacBook-Pro ~ % file AWSCLIV2.pkg 
AWSCLIV2.pkg: HTML document text, ASCII text, with very long lines (342)
Apple@MacBook-Pro ~ % curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 56.6M  100 56.6M    0     0  2881k      0  0:00:20  0:00:20 --:--:-- 3168k
Password:
installer: Package name is AWS Command Line Interface
installer: Installing at base path /
installer: The install was successful.

