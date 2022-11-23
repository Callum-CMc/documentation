import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import JWTGenerator from '@site/src/components/JWTGenerator';

The HTTP connection between your beacon node and execution node needs to be authenticated using a [JWT token](https://jwt.io/). There are several ways to generate this JWT token:

1. We generated one random for you (<a href="#generate-jwt" onClick={()=>{ javascript:window.location.reload(); }}>regenerate</a>), place it into the `jwtsecret` file:

<JWTGenerator />

2. Use an execution or consensus client to generate the `jwtsecret` file (check their documentation).
3. Use an online generator like [this](https://seanwasere.com/generate-random-hex/). Copy and paste this value into a `jwtsecret` file.
4. Use a utility like OpenSSL to create the token via command: 

```
openssl rand -hex 32 | tr -d "\n" > "jwtsecret"
```

After generating your token, create the file by running:
```
echo 'PLACE_HERE_YOUR_TOKEN' > jwtsecret
```