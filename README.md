🌐 Deploying an Website on Apache2 Server in Amazon Ec2

1. AWS Instance Requirements
Instance Type: t2.micro

🐧 Ubuntu OS for web hosting

1. Update Package List 🔄
sudo apt update
2. Create a Deployment Directory 📂
mkdir website_Deployment
cd website_Deployment

3.Install Apache2 Web Server 
sudo apt install apache2 -y

4. Start,enable,status Apache2 Service ▶️
sudo systemctl start apache2
sudo systemctl enable apache2
sudo systemctl status apache2

5.Check Your Server's Public IP Address 🌐
curl http://checkip.amazonaws.com

6.**Download a Website Template **
wget https://www.tooplate.com/zip-templates/2126_antique_cafe.zip

7. Extract
unzip 2126_antique_cafe.zip

8.. Replace Template Content 🔄
Replace yourname in the below command with your desired name.

sed -i 's/Antique/yourname/g' 2126_antique_cafe/index.html
Description: This command uses the sed command to replace the word "Antique" with "yourname" in the template's HTML file. Replace "yourname" with your desired website name.

10. Remove Default Apache2 Index Page (Again) 🗑️
sudo rm -r /var/www/html/index.html

11. Copy Template Files to Apache2 Document Root 📂
sudo cp -r 2126_antique_cafe/* /var/www/html/

12. Restart the service
    sudo systemctl restart apache2

13.Check Your Server's Public IP Address 🌐
   curl http://checkip.amazonaws.com
