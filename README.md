## 🧭 **GUÍA RÁPIDA DE MYSQL (MySQL CLI / PowerShell)**

---

### 🔐 **1. Conectarse a MySQL**
Desde PowerShell:

```powershell
mysql -u root -p
```

---

### 🏗️ **2. Crear una base de datos**
```sql
CREATE DATABASE nombre_db;
```

🔹 Ejemplo:
```sql
CREATE DATABASE tienda;
```

---

### 👤 **3. Crear un usuario**
```sql
CREATE USER 'usuario'@'localhost' IDENTIFIED BY 'contraseña';
```

🔹 Ejemplo:
```sql
CREATE USER 'juan'@'localhost' IDENTIFIED BY '12345';
```

---

### 🛡️ **4. Dar permisos a un usuario sobre una base de datos**
```sql
GRANT ALL PRIVILEGES ON nombre_db.* TO 'usuario'@'localhost';
```

🔹 Ejemplo:
```sql
GRANT ALL PRIVILEGES ON tienda.* TO 'juan'@'localhost';
```

✅ Luego, aplica los cambios con:

```sql
FLUSH PRIVILEGES;
```

---

### 🧾 **5. Ver todos los usuarios**
```sql
SELECT User, Host FROM mysql.user;
```

---

### 🔍 **6. Ver los privilegios de un usuario**
```sql
SHOW GRANTS FOR 'usuario'@'localhost';
```

---

### ❌ **7. Revocar permisos**
```sql
REVOKE ALL PRIVILEGES ON nombre_db.* FROM 'usuario'@'localhost';
```

---

### 🧹 **8. Eliminar un usuario**
```sql
DROP USER 'usuario'@'localhost';
```

---

### 🧨 **9. Eliminar una base de datos**
```sql
DROP DATABASE nombre_db;
```

---

### 📂 **10. Exportar (respaldo) una base de datos**
Desde PowerShell (fuera del prompt de MySQL):

```powershell
mysqldump -u root -p nombre_db > respaldo.sql
```

---

### 📥 **11. Importar una base de datos desde un respaldo**
Primero crea la base de datos:

```sql
CREATE DATABASE nombre_db;
```

Luego, desde PowerShell:

```powershell
mysql -u root -p nombre_db < respaldo.sql
```

---

### 📜 **12. Ver tablas de una base de datos**
Primero selecciona la base:

```sql
USE nombre_db;
```

Luego:

```sql
SHOW TABLES;
```

---

### 🔧 **13. Ver estructura de una tabla**
```sql
DESCRIBE nombre_tabla;
```

---

### 🛠️ **14. Crear una tabla de ejemplo**
```sql
CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100),
    precio DECIMAL(10,2)
);
```

---

¿Te gustaría que esta guía te la exporte como un archivo `.txt` o `.pdf`?
