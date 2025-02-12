# MikroTik Router Update Playbook
This Ansible playbook automates the process of updating MikroTik routers over SSH. The playbook connects to the routers via SSH on port `2222`, authenticates using a predefined username and password, and then runs the necessary commands to update the router’s firmware.

## How It Works:
Router List: The list of router IPs is defined in the `routers.yml` file. Each router has an associated SSH port (default is `2222`).
Credentials: The credentials for SSH login (`username: admin`, `password: admin1234`) are securely stored in the `login.yml` file.
Update Commands: Once connected to each router, the playbook runs the following commands to update the firmware:
* `/system/package/update/set channel=stable`: Set the update channel to stable.
* `/system package update check-for-updates`: Check for available updates.
* `/system package update install`: Install the updates.\
**Execution:** The playbook iterates through each router in the list and performs the update sequentially.
## How to Use:
1. Clone the repository to your local machine.
2. Ensure you have Ansible and `sshpass` installed.
3. Update the `routers.yml` file with your own router IPs if needed.
4. Ensure the `login.yml` contains the correct login credentials.
Run the playbook:
```
ansible-playbook update_mikrotik.yml
```
This playbook helps automate the tedious task of updating multiple MikroTik routers at once, making the process faster and more efficient.
____
# پلی‌بوک بروزرسانی روترهای MikroTik
این پلی‌بوک انسیبل به‌طور خودکار فرآیند بروزرسانی روترهای MikroTik را از طریق SSH انجام می‌دهد. پلی‌بوک به روترها از طریق پورت `2222` متصل می‌شود، با استفاده از نام کاربری و پسورد از پیش تعریف شده وارد سیستم می‌شود و سپس دستورات لازم برای بروزرسانی سیستم‌عامل روتر را اجرا می‌کند.

نحوه عملکرد:
لیست روترها: لیست IP روترها در فایل `routers.yml` تعریف شده است. برای هر روتر یک پورت SSH (پیش‌فرض `2222`) مشخص شده است.
اطلاعات احراز هویت: اطلاعات نام کاربری و رمز عبور برای ورود SSH (`نام کاربری: admin`، `رمز عبور: admin1234`) به‌صورت امن در فایل `login.yml` ذخیره شده است.
دستورات بروزرسانی: پس از اتصال به هر روتر، پلی‌بوک دستورات زیر را برای بروزرسانی سیستم‌عامل اجرا می‌کند:
* `/system/package/update/set channel=stable`: تنظیم کانال بروزرسانی به stable.
* `/system package update check-for-updates`: بررسی به‌روزرسانی‌های موجود.
* `/system package update install`: نصب به‌روزرسانی‌ها.\
## نحوه استفاده:
* مخزن را در سیستم محلی خود کلون کنید.
* اطمینان حاصل کنید که Ansible و `sshpass` نصب شده‌اند.
* در صورت نیاز، فایل `routers.yml` را با IPهای روتر خود به‌روز کنید.
* اطمینان حاصل کنید که اطلاعات ورود در فایل `login.yml` صحیح است.
## پلی‌بوک را اجرا کنید:
```
ansible-playbook update_mikrotik.yml
```
این پلی‌بوک به‌طور خودکار فرآیند بروزرسانی چندین روتر MikroTik را انجام می‌دهد و کار را سریع‌تر و کارآمدتر می‌کند.



