<?php
    class Validacion{
        
        function CadenaVacia($Cadena){
            
            if(Validacion::ElimEsp($Cadena) == ""){
                return TRUE;
            }
            
            return FALSE;
        }
        
        //Regresa un string sin los espacios del parametro
        //$Cadena(string)
        function ElimEsp($Cadena){
            
            $strTmp = "";
            for($i = 0; $i < strlen($Cadena); $i++){
                if($Cadena{$i} != " "){
                    $strTmp .= $Cadena{$i};
                }
            }
            
            return $strTmp;
        }
       
        //Regresa true si el tamaño del primer parametro es igual al segundo parametro false si no
        //Cadena(string), Size(int); 
        function NumChar($Cadena, $Size){
            
            if(strlen($Cadena) == $Size){
                return TRUE;
            }
            
            return FALSE;
        }
        
        //Regresa un string con todos los caracteres del parametro en Minusculas
        //$Cadena(string)
        function  Minusculas($Cadena){
            return strtolower($Cadena);
        }
        
        //Regresa un string con todos los caracteres del parametro en Mayusculas
        //$Cadena(string)
        function  Mayusculas($Cadena){
            return strtoupper($Cadena);
        }
        
        //Regresa un string con el primer caracter de cada palabra del parametro en Mayusculas
        //y los demas en minusculas
        //$Cadena(string)
        function  LetrasCapitales($Cadena){
            return ucwords(Validacion::Minusculas($Cadena));
        }
        
        /*Regresa true si el parametro solo contiene letras 
          y false si contiene almenos un numero o caracter especial*/
        //$Cadena(tring)
        function  ContieneSoloLetras($Cadena){
            return Validacion::Verificar("^[a-z]+$",$Cadena);
        }

        private function Verificar($Prt, $Cadena){
            return eregi($Prt,$Cadena);
        }
        
        //Regresa FALSE si es un número sino regresa TRUE
        function ContieneSoloNumeros($Cadena){
            return !is_numeric($Cadena);
        }
        
        //Regresa TRUE si es un entero sino regresa FALSE
        function ContieneSoloEnteros($Cadena){
            return is_int($Cadena);
        }
    }

/* 
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

