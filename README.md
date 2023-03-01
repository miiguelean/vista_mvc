# Vista del MVC

Se definira la vista con la que se trabajara.
## De que son responsables las vistas

Recibir datos del modelo y los muestra al usuario.

Tienen un registro de su controlador asociado (normalmente porque además lo instancia).

Pueden dar el servicio de "Actualización()", para que sea invocado por el controlador o por el modelo (cuando es un modelo activo que informa de los cambios en los datos producidos por otros agentes).

## Ejemplo
Este ejemplo es para hacer un insert en una tabla productos, y al hacer click a enviar los datos se mandan al controlador donde se juntan los valores con la instruccion sql del modelo y se envian a la base de datos

```php
<form id="frmInsert" name="frmInsert" action="controlador.php" method="post" onsubmit="return validar();">
		<input id="idProd" name="idProd" type="text" placeholder="id Producto" value="<?php echo @$cat_mod[0][0]; ?>" hidden/>
		<div class="row">
			<h1>Registrar Producto</h1>
		  <span>
		    <input class="balloon" id="nombre" name="nombre" type="text" placeholder="Nombre" value="<?php echo @$cat_mod[0][1]; ?>" onkeypress="return Vname();" required/><label for="Nombre">Nombre</label>
		  </span>
		  <span>
		    <input class="balloon" id="cant" name="cant" type="text" placeholder="Cantidad" value="<?php echo @$cat_mod[0][2]; ?>" onkeypress="return Vcant();" required/><label for="Cantidad">Cantidad</label>
		  </span>
		  <span>
		    <input class="balloon" id="precio" name="precio" type="text" placeholder="Precio" value="<?php echo @$cat_mod[0][3]; ?>" onkeypress="return Vprecio();"  required/><label for="Precio">Precio</label>
		  </span>
		<input type="submit" name="btnEnviar" id="btnEnviar" value="<?php if(isset($_GET['id_mod'])) {
			echo 'Modificar';
		}
		else
		{
			echo 'Registrar';
		}
		 ?>">
		
		</div>	
	</form>
```
