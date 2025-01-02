# Integrating Wallet Connect in a Frontend Application

1. Introduction

Learn to integrate Wallet Connect to enable user authentication and transactions in a React.js application.

2. Prerequisites

Node.js installed.

Basic knowledge of React.js.

WalletConnect SDK.


3. Setup the React Project

1. Initialize the project:

npx create-react-app neo-wallet-connect
cd neo-wallet-connect


2. Install dependencies:

npm install @walletconnect/client
npm install neo-wallet-adapter-react



4. Implement WalletConnect

1. Import WalletConnect:

import WalletConnect from "@walletconnect/client";
import QRCodeModal from "@walletconnect/qrcode-modal";


2. Connect to Wallet:

const connector = new WalletConnect({
    bridge: "https://bridge.walletconnect.org",
});

if (!connector.connected) {
    connector.createSession().then(() => {
        QRCodeModal.open(connector.uri);
    });
}


3. Handle Connection Events:

connector.on("connect", (error, payload) => {
    if (error) throw error;
    console.log(payload);
});



5. Test the Application

1. Start the application:

npm start


2. Scan the QR code with a compatible wallet and execute a sample transaction.
