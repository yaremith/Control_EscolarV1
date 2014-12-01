<!doctype html>

<html>
    <head>
    <meta charset="utf-8">
    <title>Verificar Pag</title>
    </head>   
    
    <body>
        <?php
        
            require_once('ClaseValidacion.php');
            ini_set("../soap.wsdl_cache_enabled", "0");
            require_once("../nusoap/lib/nusoap.php");

            $cliente = new nusoap_client("http://192.168.2.102:8080/WebService/wbs_actualizarAlumno.php?wsdl");
            $cliente2 = new nusoap_client("http://192.168.2.102:8080/WebService/wbs_buscarAlumno.php?wsdl");
            
            $matricula = $_POST['FrmMatricula'];
            $nombre =  $_POST['FrmNombre'];
            $apellidop =  $_POST['FrmApellidoPaterno'];
            $apellidom =  $_POST['FrmApellidoMaterno'];
            $edad =  (int)($_POST['FrmEdad']);
            
            $matriculaJson = json_encode($matricula);
                $nombreJson = json_encode($nombre);
                $apellidopJson = json_encode($apellidop);
                $apellidomJson = json_encode($apellidom);
                $edadJson = json_encode($edad);

            
            if(Validacion::CadenaVacia($matricula) || Validacion::CadenaVacia($nombre) || Validacion::CadenaVacia($apellidop) || Validacion::CadenaVacia($apellidom))
                {
                echo "<script>alert('Rellene todos los campos.');</script>";
                echo "<script>window.location = '../Seleccion/FrmActualizarAlumno.php';</script>";
            }
            
            if ($cliente2->call("buscarAlumno", array("Matricula_Alumno" => $matriculaJson)))
            {
                

                if($cliente->call("actualizarAlumno", array("Matricula_Alumno" => $matriculaJson, "Nombre" => $nombreJson, 
                    "ApellidoPat" => $apellidopJson, "ApellidoMat" => $apellidomJson, "Edad" => $edadJson))) 
                    {                
                    echo "<script>alert('Datos del Alumno con matrícula $matricula modificados correctamente.');</script>";
                    echo "<script>window.location = '../FrmIndex.php';</script>";
                    }
                               
            }
            else
            {                                                
                  echo "<script>alert('No existe la matrícula en la BD.');</script>";
                    echo "<script>window.location = '../Seleccion/FrmActualizarAlumno.php';</script>";                               
            }
        ?>        
    </body>
</html>

