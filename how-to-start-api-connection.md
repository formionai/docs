# 🔑 How to Start with Formion AI? API Connection?

**It's important to have some USDT balance ( 10$ at least) on your Futures account on Binance ( or UTA on Bybit ) for Formion to be able to check your API keys properly!**

## For Binance:

For [Binance](https://binance.com) go to User icon 👤 and [API Managament](https://www.binance.com/en/my/settings/api-management)

<figure><img src=".gitbook/assets/binance1.png" alt=""><figcaption></figcaption></figure>

Then click on **Create API** button and choose **System generated**, put any name you want and click **Next**

<figure><img src=".gitbook/assets/binance2.png" alt=""><figcaption></figcaption></figure>

You will get **API keys** but you need now to edit it and put a **whitelisted IPs** from Formion settings page and then check **Enable Futures** and **Enable Spot & Margin Trading,** save it and copy both **APY key** and **Secret key** and put into **Settings** page on **Formion**, fill your **password** and click on **Submit.**

<figure><img src=".gitbook/assets/binance3.png" alt=""><figcaption></figcaption></figure>

Now go to the **Formion** [Settings page](https://formion.ai/user/settings), choose **Binance** as the exchange, and add **all** of the IP addresses below to your API key's **IP whitelist** (Restrict access to trusted IPs only):

```
194.163.189.111
207.180.195.116
45.142.214.88
51.158.66.203
89.187.162.131
185.220.101.47
209.126.7.214
176.103.56.19
146.59.227.90
163.172.140.55
193.42.96.122
38.91.107.244
141.98.252.130
85.239.34.177
102.165.48.219
198.54.117.200
77.83.36.142
156.146.59.31
```

{% hint style="info" %}
Add **every** IP in the list. Formion runs behind a rotating pool of execution gateways for redundancy and DDoS protection, so your API key must allow all of them — only a subset is active at any moment. You can paste the same list on the Formion Settings page to verify it matches.
{% endhint %}

**Note: Its important to change mode to HEDGE and Perpetual Margin Mode to CROSS for each USDT pair on Binance Futures!**\\

<figure><img src=".gitbook/assets/sett1.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/oneway.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/hedge1.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/cross.png" alt=""><figcaption></figcaption></figure>

## For Bybit:

For Bybit the situation is the same but here if you want to use multiple bots our advice is to create each subaccount for each new bot! Also make sure your account type is UTA ( Unified Trading Account )

<figure><img src=".gitbook/assets/subacc.png" alt=""><figcaption></figcaption></figure>

Then go to [API ](https://www.bybit.com/app/user/api-management)Managament tab page and click on **Create New Key and enable Google 2FA if you are using it ( It's recommended!)**

<figure><img src=".gitbook/assets/bybit1.png" alt=""><figcaption></figcaption></figure>

Click on System-generated API Keys

<figure><img src=".gitbook/assets/bybit2.png" alt=""><figcaption></figcaption></figure>

Now go to the Formion [Settings page](https://formion.ai/user/settings) and choose Bybit as your exchange. Whitelist the **same full IP list shown above** (in the Binance section) on your Bybit API key.

Now here it's very important to check **Read-Write** permission mode and also enable **Only IPs** mode with all of those IPs.

<figure><img src=".gitbook/assets/newkey1.png" alt=""><figcaption></figcaption></figure>

Make sure you have checked all those, just Account Transfer and Subaccount Transfer is not required!

<figure><img src=".gitbook/assets/bybit4.png" alt=""><figcaption></figcaption></figure>

Now you will get API key and API Secret and copy both and paste to Formion Settings page, fill with your password and Submit it!

<figure><img src=".gitbook/assets/newkey23.png" alt=""><figcaption></figcaption></figure>

\
Also make sure its Hedge Mode and Cross Margin mode enabled for all USDT pairs!\\

<figure><img src=".gitbook/assets/cross0.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/cross1.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/hedge0.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/hedge2.png" alt=""><figcaption></figcaption></figure>

Please check Apply to all USDT pairs!\
\
To test everything is passed well go to Formion Portfolio Settings\
and you will see something like this for Binance\\

<figure><img src=".gitbook/assets/portfolio.png" alt=""><figcaption></figcaption></figure>

Or for Bybit

<figure><img src=".gitbook/assets/port2.png" alt=""><figcaption></figcaption></figure>

### If you are able to see your portfolio, congrats! You are now ready to use Formion Trading App!
