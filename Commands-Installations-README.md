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
