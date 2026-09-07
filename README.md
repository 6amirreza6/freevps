# Create By 6amirreza6
```markdown
Instructions are provided in Farsi and English below. Please read all the content thoroughly.
دستورالعمل‌ها به زبان‌های فارسی و انگلیسی در زیر ارائه شده‌اند. لطفاً تمام مطالب را به طور کامل مطالعه کنید.

-----------------------------------------------------------

# Free Windows VPS — Using the RDP & Tailscale Method
# سرور مجازی ویندوز رایگان - با استفاده از روش RDP و Tailscale

---

## 🇮🇷 فارسی

### مرحله ۱: فورک کردن ریپازیتوری
صفحه را فورک کنید.

### مرحله ۲: ساخت حساب Tailscale
در [Tailscale.com](https://tailscale.com) یک حساب بسازید.

### مرحله ۳: نصب برنامه Tailscale
برنامه‌ی Tailscale را دانلود و نصب کنید.

### مرحله ۴: ساخت Auth Key
1. وارد سایت Tailscale.com شوید.
2. به بخش **Settings** بروید و روی **Keys** بزنید.
3. از بخش **Auth keys** روی **Generate auth key...** بزنید.
4. در قسمت **Description** یک نام دلخواه برای کلید بگذارید.
5. گزینه‌ی **Reusable** را روشن کنید.
6. در قسمت **Expiration** عدد `90` را قرار دهید (دلخواه است).
7. گزینه‌ی **Ephemeral** را هم روشن کنید.
8. روی **Generate key** بزنید و کلید نمایش داده‌شده را کپی کنید.

### مرحله ۵: افزودن Secret در گیت‌هاب
1. وارد گیت‌هاب شوید و ریپازیتوری‌ای که فورک کرده‌اید را باز کنید.
2. روی **Settings** ریپازیتوری بزنید.
3. وارد بخش **Secrets and variables** شوید و روی **Actions** بزنید.
4. از بخش **Repository secrets** روی **New repository secret** بزنید.
5. در قسمت **Name** مقدار زیر را وارد کنید:
   ```

   TAILSCALE_AUTHKEY
   ```
6. در قسمت **Secret** همان کلیدی که از Tailscale.com کپی کرده بودید را قرار دهید.

### مرحله ۶: اجرای Workflow
1. از گیت‌هاب، بخش **Actions** ریپازیتوری فورک‌شده را باز کنید.
2. از منوی کنار صفحه روی **Windows Cloud RDP** بزنید.
3. روی **Run workflow** بزنید و سپس دکمه‌ی سبز رنگ **Run workflow** را بزنید.
4. صفحه‌ی جدیدی باز می‌شود؛ روی **build** بزنید.
5. گزینه‌ی سوم یعنی **Install & Connect Tailscale VPN** را بزنید (کمی طول می‌کشد تا اطلاعات نمایش داده شود).
6. مقادیر **Username**، **Password** و **Tailscale IP** را ذخیره کنید.

### مرحله ۷: اتصال به Tailscale
وارد اپ Tailscale شوید و به شبکه‌ی Tailscale کانکت شوید.

### مرحله ۸ (پایان): اتصال با Remote Desktop
1. برنامه‌ی **Remote Desktop Connection** ویندوز را باز کنید.
2. مقدار **Tailscale IP** را وارد کرده و روی **Connect** بزنید.
3. **Username** و **Password** ذخیره‌شده را وارد کنید.
4. روی **OK** بزنید. تمام! ✅

> **نکته:** این سرویس فقط بین ۶ تا ۴۸ ساعت فعال می‌ماند. در صورت خاموش شدن، دوباره به بخش **Actions** بروید، روی **Windows Cloud RDP** و سپس **Run workflow** بزنید، دکمه‌ی سبز **Run workflow** را بزنید، در صفحه‌ی جدید روی **build** و سپس گزینه‌ی سوم **Install & Connect Tailscale VPN** بزنید و مقادیر جدید را ذخیره کنید. در صورت دانلود هر فایلی از اینترنت، از حجم اینترنت شما کم نمی‌شود.

---

## 🇬🇧 English

### Step 1: Fork the Repository
Fork this page.

### Step 2: Create a Tailscale Account
Create an account at [Tailscale.com](https://tailscale.com).

### Step 3: Download the Tailscale App
Download and install the Tailscale application.

### Step 4: Generate an Auth Key
1. Log in to Tailscale.com.
2. Go to **Settings** and click **Keys**.
3. Under **Auth keys**, click **Generate auth key...**.
4. Enter any name you like in the **Description** field.
5. Turn on **Reusable**.
6. Set **Expiration** to `90` (optional).
7. Turn on **Ephemeral**.
8. Click **Generate key** and copy the key shown.

### Step 5: Add the Secret to GitHub
1. Log in to GitHub and open the repository you forked.
2. Go to the repository's **Settings**.
3. Go to **Secrets and variables**, then click **Actions**.
4. Under **Repository secrets**, click **New repository secret**.
5. For **Name**, enter:
   ```

   TAILSCALE_AUTHKEY
   ```
6. For **Secret**, paste the key you copied from Tailscale.com.

### Step 6: Run the Workflow
1. On GitHub, open the **Actions** tab of your forked repository.
2. From the sidebar, click **Windows Cloud RDP**.
3. Click **Run workflow**, then click the green **Run workflow** button.
4. A new page will appear; click **build**.
5. Click the third option, **Install & Connect Tailscale VPN** (it may take a moment to load).
6. Save the **Username**, **Password**, and **Tailscale IP** provided.

### Step 7: Connect to Tailscale
Open the Tailscale app and connect to your Tailscale network.

### Step 8 (Final): Connect via Remote Desktop
1. Open the **Remote Desktop Connection** app on Windows.
2. Enter the **Tailscale IP** and click **Connect**.
3. Enter the saved **Username** and **Password**.
4. Click **OK**. Done! ✅

> **Note:** This service only stays active for 6 to 48 hours. If it shuts down, go back to **Actions**, click **Windows Cloud RDP**, then **Run workflow**, click the green **Run workflow** button, then on the new page click **build** and the third option **Install & Connect Tailscale VPN**, and save the new values. Downloading files from the internet does not use your own internet data.
```
