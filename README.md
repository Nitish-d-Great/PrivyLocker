# PrivyLocker

**Privacy-Focused DigiLocker on Solana (Inco Lightning Consumer Track)**

PrivyLocker is a consumer web application that allows users to store personal documents privately and share only selected attributes (e.g., "Age > 18") with verifiers, without revealing the full document. It leverages Solana for ownership and data registry, and **Inco Lightning** for confidential computing and privacy preservation.

## 🚀 Featues

- **Client-Side Encryption**: Documents are encrypted in the browser (AES-256-GCM) before upload.
- **Selective Disclosure**: Share specific fields or proofs (e.g., Age Proof) without exposing sensitive PII.
- **Confidential State**: Uses Inco Network to manage private data types and access control policies on-chain.
- **Revocable Access**: Grant temporary access to verifiers and revoke it instantly.
- **Verifiable**: Verifiers receive cryptographic proof of data authenticity.

## 🏆 Inco Consumer Track Fit

PrivyLocker is designed specifically for the **Consumer** track:
1.  **Mass Adoption UX**: Simple "Dropbox-like" interface for non-technical users.
2.  **Privacy Utility**: Solves a real-world problem (sharing ID without risk) using Inco's confidential smart contracts.
3.  **Performance**: Built with a hybrid architecture (Off-chain storage + On-chain Logic) to ensure "native app speed" while maintaining robust security.

## 🛠 Tech Stack

- **Frontend**: Next.js 14 (App Router), TypeScript, TailwindCSS, Lucide Icons.
- **Wallet**: Solana Wallet Adapter (Phantom/Solflare).
- **Backend**: Node.js, Express, Multer (Mock Storage/IPFS Relay).
- **Blockchain**:
    - **Solana Devnet**: Anchor Program for document registry.
    - **Inco Lightning**: Confidential computing integration for private fields access control.

## 📦 Installation

### Prerequisites
- Node.js v18+
- Rust & Cargo (for Program)
- Solana CLI
- Anchor CLI

### Setup

1.  **Clone the Repository**
    ```bash
    git clone <repo-url>
    cd PrivyLocker
    ```

2.  **Frontend Setup**
    ```bash
    cd app
    npm install
    npm run dev
    ```
    Open `http://localhost:3000`.

3.  **Backend Setup**
    ```bash
    cd ../api
    npm install
    npm run dev
    ```
    Runs on `http://localhost:3001`.

4.  **Solana Program**
    ```bash
    cd ../
    anchor build
    anchor deploy --provider.cluster devnet
    ```
    *Note: Ensure you have devnet SOL in your wallet.*

## 🧪 Testing

1.  **Upload Flow**: Go to Dashboard -> Upload. Select a file. Watch it get encrypted and "uploaded".
2.  **Verification**: After upload (mock), generate a share link. Open the link in Incognito mode to view the Verifier page.
3.  **Revocation**: (Coming Soon) Revoke access from the Dashboard.

## 🛡️ Security

- **End-to-End Encryption**: The server never sees the raw file.
- **Ephemeral Access**: Share links can expire.
- **Confidential Computing**: Inco ensures that even validators cannot see private fields.

---

*Built for Solana Privacy Hackathon 2026*
