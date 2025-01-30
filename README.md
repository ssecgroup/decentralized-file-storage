Frontend Overview:
The frontend for this project is a web interface that allows users to interact with the decentralized file storage and access control system powered by the Filecoin Virtual Machine (FVM). Through this UI, users can upload files, manage access control, and view file details such as ownership, access rights, and expiration times. The frontend communicates with the blockchain through Web3, allowing users to interact with the smart contract and execute actions like uploading files, granting or revoking access, and checking file access status.

Key Features:
File Upload Interface:

Users can upload files to the system by providing a file hash (e.g., IPFS hash or CID) and specifying an expiration date.
The UI will validate the expiration time and ensure it is set in the future.
Upon successful upload, the file is registered on the blockchain, and the user becomes the owner of the file.
The uploaded file's details (hash and expiration time) are displayed to the user.
Grant Access:

File owners can grant access to specific users (by their Ethereum address) for any uploaded file.
The system updates the file's access control list to include the newly authorized user.
Once access is granted, both the owner and the user are notified via event-driven updates in the UI.
Revoke Access:

File owners can also revoke access from previously authorized users.
When access is revoked, the user is no longer able to interact with or view the file unless access is granted again.
The UI provides a simple interface to manage these permissions and reflects changes in real-time.
File Access Check:

Users can check whether they have access to a file by entering the file hash.
The system will show whether the user has access, if they are the owner, or if the file's access has expired.
The file’s expiry date is also displayed, helping users understand whether they can still interact with the file or if access is no longer valid.
File List & Details:

The UI displays a list of files that the logged-in user owns, including key metadata such as:
File hash
Expiry date
Each file entry allows users to manage access permissions (grant/revoke) or view the file's access status.
Expiration Handling:

Users are notified if a file’s access period has expired.
The UI makes it clear when a file is no longer accessible to any users except the owner.
Expired files are visually differentiated from active ones, helping users quickly identify files that can no longer be accessed.
User Workflow:
Upload a File:

The user enters the file hash (or CID) and sets an expiration date.
The contract function uploadFile is called to upload the file, and the file details are shown on the frontend.
Grant Access:

The user selects a file and provides the address of the user to grant access.
The frontend calls the grantAccess function, updating the access control list and triggering an event to notify all parties.
Revoke Access:

The file owner can select a user and revoke their access, updating the file's access control list via the revokeAccess function.
Check Access:

The user can input a file hash to check if they have access to it and whether the file has expired.
Display File Information:

The frontend will list all files uploaded by the user, including access status and expiration dates.
Technologies Used:
React.js for building the frontend interface.
Web3.js (or ethers.js) for interacting with the Ethereum blockchain and the Filecoin smart contract.
IPFS/Filecoin for decentralized file storage and access control.
Bootstrap/Material UI for styling and creating a responsive design.
UI Flow:
Home Page: Displays the list of files the user has uploaded, with options to upload new files and manage access.
File Upload Page: Allows users to input file details and set an expiration time for the file.
File Access Management: Lets users manage file access permissions for other users (grant/revoke).
File Access Check: A form for users to check if they have access to a specific file by entering the file hash.
Security Considerations:
File Ownership: Only the file owner can grant or revoke access to the file.
Access Expiry: File access will automatically expire after the specified timestamp, and expired files cannot be accessed.
Smart Contract Validation: The smart contract ensures that only valid operations are performed (e.g., only the file owner can modify access).
How to Interact with the Frontend:
Connect Wallet: The user connects their Ethereum wallet (MetaMask or other supported wallets) to the frontend to interact with the smart contract.
Perform Actions: Users can interact with the frontend to upload files, manage access, and view file status.
Submit Transactions: Actions like uploading files, granting/revoking access will submit transactions to the blockchain, which the user must approve in their wallet.
