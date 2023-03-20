# How to renew SSL with certbot :closed_lock_with_key:
* Check if snap installed with:
  ``` bash
  snap version
  ```
* Otherwise install snap:
  ``` bash
  sudo apt-get install snapd
  sudo snap install core; sudo snap refresh core
  ```
* Remove any certbot packages
  ```bash
  sudo apt-get remove certbot
  ```
* Install Certbot
  ```bash
  sudo snap install --classic certbot
  ```
* Prepare the Certbot command
  ```bash
  sudo ln -s /snap/bin/certbot /usr/bin/certbot
  ```
* Check certbot version
  ```bash
  sudo certbot --version
  ```
___
## Secure Nginx with Let's Encrypt
* Test certbot
    ```bash
    sudo certbot --nginx --test-cert
    ```
* Go to browser and check STAGING certificate
* Issue real certificate
    ```bash
    sudo certbot --nginx
    ```
* Go to browser and check certificate
* Test renewal
    ```bash
    sudo certbot renew --dry-run
    ```
* Check systemctl times
    ```bash
    systemctl list-timers
    ```
