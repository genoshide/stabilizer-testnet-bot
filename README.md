# Stabilizer Testnet Automations Bot

### Description
Stabilizer Testnet Automations Bot is an automated Python script designed to interact with various features within the Stabilizer Testnet ecosystem. It streamlines routine tasks such as daily check-ins, claiming faucet tokens, swapping tokens on supported dApps, adding liquidity, sending tokens, completing missions, and handling referral activities automatically.

The bot helps users efficiently participate in Stabilizer Testnet activities by automating repetitive actions and maintaining consistent interaction with the platform.

### Setup Instructions:
-  Python `3.7 or higher` (recommended 3.9 or 3.10 due to asyncio usage).
-  pip (Python package installer)

### Features
-  **Proxy Support**: Supports both mobile and regular proxies.
-  **Multithread support**: Run your bot faster
-  **Faucet**: Support auto claiming `official faucet`
-  **Captcha Solver**: Completing `captcha` for faucet
-  **Check-in**: Support Daily Checkin without missing a day
-  **Auto Referral**: Support to Register a new account with Referral
-  **Wallet Handling**: `Shuffle` wallets and `configure` pauses between operations.
-  **Auto Send Token**: Support sending token to an address listed on `wallets.txt`
-  **Token Swaps**: Support Swapping on Available Pair
-  **Liquidity**: Support Provide Liquidity on Dapps
-  **WRAP/UNWRAP**: Support Swap and Unwrap via contract
-  **Quest Completion**: Support automatic quest completions
-  **Gas Refueling**: Refill gas when it going to 0.
-  **Access Token & User Agent**: Support saving session for `AccessToken & UserAgent`

### Usage
#### Installation and startup

1. Clone this repository:
   ```bash
   git clone https://github.com/genoshide/stabilizer-testnet-bot.git
   cd stabilizer-testnet-bot
   ```
2. Create virtual environment (optional but recomended)
   ```bash
   python -m venv venv
   ```

   Once created, you need to activate the virtual environment. The method for activating it varies depending on your operating system:
   
    #### On Windows
    ```bash
    venv\Scripts\activate
    ```
    #### On macOS/Linux
    ```bash
    source venv/bin/activate
    ```
3. Install the dependencies:
   The requirements.txt ensure your requirements.txt looks like this before installing:
   ```yaml
   aiohttp==3.11.10
   asyncio
   requests>=2.31.0
   web3>=6.0.0
   eth-account>=0.10.0
   pyjwt>=2.8.0
   python-dotenv>=1.0.1
   colorama>=0.4.6
   aiofiles==23.2.1
   curl-cffi==0.10.0
   eth-abi==5.2.0
   cryptography==36.0.0
   fake-useragent==1.5.1
   aiohttp-socks==0.9.1
   eth-utils==5.3.0
   pytz==2024.1
   ```
   Then install:
   ```bash
   pip install -r requirements.txt
   ```    

### Configuration
All settings are in `.env`. Key options include:

#### Feature Settings
```yaml
USE_PROXY=false
MAX_THEADS=10
MAX_THEADS_NO_PROXY=1

REF_CODE="xxx"
AUTO_FAUCET=false
AUTO_CHECKIN=false
AUTO_QUESTS=false
FAROSWAP=false

AUTO_SEND=false
NUMBER_SEND=3
AMOUNT_SEND=[0.001,0.0022]
```

- `TYPE_CAPTCHA`: Enter value [ `2captcha`, `anticaptcha` or `monstercaptcha` ]
- `WEBSITE_KEY`: You don't need to change this.
- `RPC_URL`: You can get better RPCs with https://zan.top/, register and replace with your RPCs if needed
- `[value, value]`: These values are the minimum and maximum values that will be randomised by the bot.

#### Add your Private Key on `private_key.txt`
   ```txt
   your_private_key
   your_private_key
   ```
#### Add your Proxies on `proxies.txt`
   ```yaml
   http://user:pass@ip:port
   http://user:pass@ip:port
   ```
#### Add referral & wallet
   - Change `example.env` to `.env` and fill your referral code on `REF_CODE`
   - Fill the `wallets.txt` with your receiver token address

### Run (first module, then second module):
   ```bash
    python main.py
   ```
     
### Contributing

Submit pull requests or report issues. Ensure your code follows best practices.

### License

This project is open-source—modify and distribute as needed.
