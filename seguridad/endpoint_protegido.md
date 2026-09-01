# Endpoint Protegido

## Descripción

Endpoint que requiere autenticación para acceder.

## Funcionamiento

1. El usuario realiza una petición al endpoint.
2. El filtro de autenticación verifica el token.
3. Si el token es válido, el endpoint devuelve los datos solicitados.
4. Si el token es inválido, devuelve un error de autenticación.