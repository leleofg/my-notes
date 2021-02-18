**Instalando o cognito em uma aplicação nodejs:**

```
npm install aws-sdk
```

**Configurando o cognito:**

```
AWS.config.update({
  accessKeyId: process.env.ACCESS_KEY_ID,
  region: process.env.region,
  secretAccessKey: process.env.SECRET_ACCESS_KEY,
  apiVersion: "latest", // aqui você pode escolher a versão desejada(olhar a documentação da API ou releases da lib)
});
```

**Método para fazer login com o cognito:**

* Nesse método você precisa enviar o username definido nas configurações do cognito(o meu é o email) e o password

```
export async function cognitoSignIn(username: string, password: string) {
  const cognitoidentityserviceprovider = new AWS.CognitoIdentityServiceProvider();

  return cognitoidentityserviceprovider
    .initiateAuth({
      AuthFlow: "USER_PASSWORD_AUTH",
      AuthParameters: {
        USERNAME: username,
        PASSWORD: password,
      },
      ClientId: process.env.COGNITO_CLIENT_ID,
    })
    .promise();
}
```

**Método para fazer refresh do token com o cognito:**

* Nesse método você precisa enviar o refreshToken que vem da response do método de login(método acima)

```
export async function cognitoRefreshToken(refreshToken: string) {
  const cognitoidentityserviceprovider = new AWS.CognitoIdentityServiceProvider();

  return cognitoidentityserviceprovider
    .initiateAuth({
      AuthFlow: "REFRESH_TOKEN_AUTH",
      AuthParameters: {
        REFRESH_TOKEN: refreshToken,
      },
      ClientId: process.env.COGNITO_CLIENT_ID,
    })
    .promise();
}
```