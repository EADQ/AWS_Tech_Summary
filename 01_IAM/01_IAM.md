# IAM

## Usuarios y Grupos

### IAM = Identity and Access Management
### Es un Servicio Global
### Cuenta root/raíz creada por defecto, no debe de ser utilizar ni compartida
### Los usuarios son personas dentro de tu organización, y pueden ser agrupados
### Los grupos solo tienen usuarios, no otros grupos
### Los usuarios no tienen que pertenecer a un grupo necesariamente,<br> y el usuario puede pertenecer a varios grupos a la vez

## Permisos

### A los usuarios o grupos se les pueden asignar documentos JSON llamados políticas
### Estas políticas definen los permisos de los usuarios
### En AWS se aplica el **principio de mínimo privilegio**: no dar más permisos de lo que un usuario necesita

## Estructura de las Políticas de IAM

### Consta de:
#### Version: Version del lenguaje de la política, siempre incluye "2012-10-17"
#### ID: Un identificador para la política (opcional)
#### Statement: Una o más declaraciones individuales (es obligatorio)
##### Las declaraciones constan de:
###### Sid: un identificador para la declaración (opcional)
###### Effect: Si la sentencia permite o deniega el acceso (Permitir, Denegar)
###### Principal: cuenta/usuario/rol al que aplica esta política
###### Action: lista de acciones que esta política permite o deniega
###### Resource: lista de recursos a los que aplican las acciones
###### Condition: condiciones para cuando esta política está en efecto (opcional)

## Política de Contraseñas

### Contraseñas fuertes = mayor seguridad para tu cuenta
### En AWS, puedes configurar una política de contraseñas:
#### Establecer una longitud mínima de contraseña
#### Requerir tipos de caracteres específicos:
##### Incluyendo letras mayúsculas
##### Letras minúsculas
##### Números
##### Caracteres no alfanuméricos
### Permitir a todos los usuarios de IAM cambiar sus propias contraseñas
### Requerir a los usuarios que cambien su contrseña <br>después de un tiempo (caducidad de la contraseña)
### Impedir la reutilización de la contraseña

## Multi Factor Authentication - MFA

### Los usuarios tienen acceso a tu cuenta y posiblemente pueden cambiar <br>configuraciones o eliminar recursos en tu cuenta de AWS
### **Quieres proteger tus cuentas root y los usuarios de IAM**
### MFA = contraseña que conoces + dispositivo de seguridad que posees
### **Principal Beneficio de MFA:** si una contraseña es robada o hackeada,<br> la cuenta no se ve comprometida
### Opciones de Dispositivos MFA en AWS
#### Dispositivo Virtual MFA
##### Autenticador de Google <br> (solo en el celular)
##### Authy <br> (multi-dispositivo)
#### Clave de seguridad del segundo <br>factor universal (U2F) 
##### Yubikey de Yubico
### Opciones de dispositivos MFA en AWS
#### Dispositivo MFA de llavero por Hardware <br> Proporcionado por Gemalto 
#### Dispositivo MFA de llavero por Hardware <br> ora AWS GovCloud (US) <br> Proporcionado por SurePassID

## Como Pueden los Usuarios Acceder a AWS

### Para acceder a AWS tienes tres opciones:
#### **Consola de administración de AWS** (protegida por contraseña + MFA)
#### **Interfaz de línea de comandos AWS (CLI)**: protegida por claves de acceso
#### **AWS Software Developer kit (SDK)** para el código protegido por claves de acceso
#### Las claves de acceso se generan a través de la consola de AWS
### **Las claves de acceso son secretas, como una contraseña. <br>NO hay que compartirlas**
### ID de la clave de acceso ~= nombre de usuario
### Clave de acceso secreta ~= contraseña

## Que es la CLI de AWS

### Una herramienta que permite interactuar con los servicios de AWS <br>mediante comandos en tu shell de línea de comandos
### Acceso directo a las API públlicas de los servidores de AWS
### Puedes desarrollar scripts para gestionar tus recursos
### Es de código abierto: https://github.com/aws/aws-cli 
### Alternativa al uso de la consola de administración de AWS