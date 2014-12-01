<html>
    <head>
        <meta charset="utf-8">
        <title>Actualizar Estatus</title>
    </head>
    <body>
        <?php
        
            require_once('ClaseValidacion.php');
            ini_set("soap.wsdl_cache_enabled", "0");
            require_once("../nusoap/lib/nusoap.php");
            $cliente = new nusoap_client("http://192.168.2.102:8080/WebService/wbs_actualizarEstatus.php?wsdl");
            $cliente2 = new nusoap_client("http://192.168.2.102:8080/WebService/wbs_buscarAlumno.php?wsdl");

            $matricula = $_POST['matricula'];
            $matriculaJson = json_encode($matricula);
            $cadenaEstatus = $_POST['estatus'];        

            if($cadenaEstatus == 'activo')            
                $cadenaEstatusJon = true; //Se cambia el estatus dependiendo de como este el Id en la Base de Datos
            else
                $cadenaEstatusJon = false;        

            if(Validacion::CadenaVacia($matricula)){        
                echo "<script>alert('Igrese la matrícula.');</script>";
            }

            else{
                
                if ($cliente2->call("buscarAlumno", array("Matricula_Alumno" => $matriculaJson))){                

                    if($cliente->call("actualizarEstatus", array("Matricula_Alumno" => $matriculaJson, "Nuevo_Estatus" => $cadenaEstatusJon))){   
                        echo "<script>alert('Estatus modificado correctamente');</script>";
                    }

                    else{
                        echo "<script>alert('Error, el alumno no fue modificado');</script>";
                    }                                        
                }

                else{
                    echo "<script>alert('No existe la matrícula en la BD.');</script>";
                }                                        
            }
            
            echo "<script>window.location = '../Seleccion/FrmActualizarEstatusAlumno.php';</script>";
        ?>
    </body>
</html>

