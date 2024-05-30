## API Documentation

### 1. Set Callback URL
#### Description
Set the callback URL via Telegram and return the user information bound to the address.

#### Request
- **URL**: `/api/setCallbackUrl`
- **Method**: POST
- **Request Parameters**:
  - `url` (string): Callback URL

#### Request Example
```json
{
  "url": "https://example.com/callback"
}
```

#### Response
- **Status Code**: 200 OK
- **Response Body**:
  - `userId` (string): User ID
  - `fingerprint` (string): User fingerprint
  - `depositAddress` (string): Deposit address
  - `withdrawalAddress` (string): Withdrawal address
  - `parentUserId` (string): Parent user ID
  - `depositCount` (integer): Deposit count
  - `betCount` (integer): Bet count
  - `agentAirdropTrxBalances` (object): Agent airdrop TRX balances, format `{agentName: airdropTrxBalance}`

#### Response Example
```json
{
  "userId": "123456",
  "fingerprint": "unique_fingerprint",
  "depositAddress": "TRX_deposit_address",
  "withdrawalAddress": "TRX_withdrawal_address",
  "parentUserId": "parent123",
  "depositCount": 5,
  "betCount": 10,
  "agentAirdropTrxBalances": {
    "andyAgency": 25
  }
}
```

### 2. User Query API
#### Description
Query and return user information.

#### Request
- **URL**: `/api/getUserInfo`
- **Method**: GET
- **Request Parameters**:
  - `userId` (string): User ID

#### Request Example
```
/api/getUserInfo?userId=123456
```

#### Response
- **Status Code**: 200 OK
- **Response Body**:
  - `userId` (string): User ID
  - `fingerprint` (string): User fingerprint
  - `depositAddress` (string): Deposit address
  - `withdrawalAddress` (string): Withdrawal address
  - `parentUserId` (string): Parent user ID
  - `depositCount` (integer): Deposit count
  - `betCount` (integer): Bet count
  - `agentAirdropTrxBalances` (object): Agent airdrop TRX balances, format `{agentName: airdropTrxBalance}`

#### Response Example
```json
{
  "userId": "123456",
  "fingerprint": "unique_fingerprint",
  "depositAddress": "TRX_deposit_address",
  "withdrawalAddress": "TRX_withdrawal_address",
  "parentUserId": "parent123",
  "depositCount": 5,
  "betCount": 10,
  "agentAirdropTrxBalances": {
    "andyAgency": 25
  }
}
```

### 3. Set User Airdrop TRX Balance
#### Description
Set the user's airdrop TRX balance.

#### Request
- **URL**: `/api/setAirdropTrxBalance`
- **Method**: POST
- **Request Parameters**:
  - `userId` (string): User ID
  - `agentName` (string): Agent name
  - `airdropTrxCount` (float): Airdrop TRX count

#### Request Example
```json
{
  "userId": "123456",
  "agentName": "andyAgency",
  "airdropTrxCount": 500.0
}
```

#### Response
- **Status Code**: 200 OK
- **Response Body**:
  - `message` (string): Operation result message

#### Response Example
```json
{
  "message": "Airdrop TRX balance set successfully."
}
```

## User Information Fields
- `userId` (string): User ID
- `fingerprint` (string): User fingerprint
- `depositAddress` (string): Deposit address
- `withdrawalAddress` (string): Withdrawal address
- `parentUserId` (string): Parent user ID
- `depositCount` (integer): Deposit count
- `betCount` (integer): Bet count
- `agentAirdropTrxBalances` (object): Agent airdrop TRX balances, format `{agentName: airdropTrxBalance}`

### API Request and Response Examples

#### 1. Set Callback URL
##### Request
```http
POST /api/setCallbackUrl
Content-Type: application/json

{
  "url": "https://example.com/callback"
}
```
##### Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "userId": "123456",
  "fingerprint": "unique_fingerprint",
  "depositAddress": "TRX_deposit_address",
  "withdrawalAddress": "TRX_withdrawal_address",
  "parentUserId": "parent123",
  "depositCount": 5,
  "betCount": 10,
  "agentAirdropTrxBalances": {
    "andyAgency": 25
  }
}
```

#### 2. User Query API
##### Request
```http
GET /api/getUserInfo?userId=123456
```
##### Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "userId": "123456",
  "fingerprint": "unique_fingerprint",
  "depositAddress": "TRX_deposit_address",
  "withdrawalAddress": "TRX_withdrawal_address",
  "parentUserId": "parent123",
  "depositCount": 5,
  "betCount": 10,
  "agentAirdropTrxBalances": {
    "andyAgency": 25
  }
}
```

#### 3. Set User Airdrop TRX Balance
##### Request
```http
POST /api/setAirdropTrxBalance
Content-Type: application/json

{
  "userId": "123456",
  "agentName": "andyAgency",
  "airdropTrxCount": 500.0
}
```
##### Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "message": "Airdrop TRX balance set successfully."
}
```
