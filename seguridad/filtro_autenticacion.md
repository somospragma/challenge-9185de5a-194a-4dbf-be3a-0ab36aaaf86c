# Filtro de Autenticación

## Descripción

Filtro/middleware que verifica la autenticación del usuario antes de permitir el acceso a los recursos.

## Funcionamiento

1. Intercepta la petición.
2. Verifica el token de autenticación.
3. Si el token es válido, permite el acceso.
4. Si el token es inválido, devuelve un error de autenticación.