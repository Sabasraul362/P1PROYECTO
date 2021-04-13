# P1PROYECTO
P1PROYECTO
package ProyectoOXXO;

public class Proyecto {

        //Atributos
        private int CodigoCliente;
        private String nombre;
        private String apellidoPaterno;
        private String apellidoMaterno;
        private String telefono;
        private String direccion;
        private int edad;
        
        //Constructor por defecto
        public Persona(){
                
        }
        //Constructor de copia
        public Persona(Persona persona){
                this.nombre=persona.nombre;
                this.apellidoPaterno=persona.apellidoPaterno;
                this.apellidoMaterno=persona.apellidoMaterno;
                this.telefono=persona.telefono;
                this.direccion=persona.direccion;
                this.edad=persona.edad;
        }
        
        //Constructor común
        public Persona(String nom, String app, String apm, String telefono, String dir, int edad,){
                this.nombre=nom;
                this.apellidoPaterno=app;
                this.apellidoMaterno=apm;
                this.telefono=telefono
                this.direccion=dir;
                this.edad=edad;
        }
        
        public String mostrarDatos(Persona persona){
                String datos="Los datos son: \n";
                datos+=persona.nombre+"\n";
                datos+=persona.apellidoPaterno+"\n";
                datos+=persona.apellidoMaterno+"\n";
                datos+=persona.telefono+"\n";
                datos+=persona.direccion+"\n";
                datos+=persona.edad+"\n";
                return datos;
        }

package pqtObjetos;

public class Principal {

        public static void main(String[] args) {
                Persona persona1=new Persona("José Roberto", "Jiménez", "Hernández", 20, "Av. El aguacate #41");
                Persona persona2=new Persona("Mayra", "Espinosa", "Sánchez", 17, "Fracc. La noche es larga #221");
                Persona persona3=new Persona("Armando", "Ruiz", "López", 33, "Calle patitos feos #87");
                
                System.out.println(persona1.mostrarDatos(persona1));
                persona1.mayorEdad(20);
                
                System.out.println(persona2.mostrarDatos(persona2));
                persona2.mayorEdad(17);
                
                System.out.println(persona3.mostrarDatos(persona3));
                persona3.mayorEdad(33);
                
                /*******************************************************/
                //Sentencias para las preguntas
                Persona persona4=new Persona();
                System.out.println(persona4.mostrarDatos(persona4));
                
                Persona persona5=new Persona(persona1);
                System.out.println(persona5.mostrarDatos(persona5));
                
                System.out.println(persona1.mostrarDatos(persona3));
        }

}

import java.util.Scanner;
import java.util.*;
import java.net.*;
import java.io.*;


 class Cliente
 {
 		public static void main(String args[] )
 		{
 				Scanner entradaTec=new Scanner(System.in);
 				try{
 					//InetAddress.getLocalHost()
 					DataOutputStream salida; /*define un flujo de salida*/
 					DataInputStream entrada;
 					Socket conexion;  //declaracion de una variable tipo socket
 				do{
 					conexion= new Socket ("192.168.0.101",5000);//("127.0.0.1",5000);/*va el ip de la maquina*/
 					salida= new DataOutputStream (conexion.getOutputStream());
 					entrada=new DataInputStream(conexion.getInputStream());
 				
 				
 					System.out.println("Dame tu consulta");
 					String x=entradaTec.nextLine();
 					if(x.equals("exit")){
 						break;
 					}
 					salida.writeUTF(x);
 					String resultado=entrada.readUTF();
 						System.out.println("\n");
 					System.out.println(resultado);
                       	conexion.close();
 				}while(true);	
 				
 				}
 				catch(UnknownHostException e ){
 					System.out.println(e);
 					System.out.println(
 						"Debe estar conectado para que esto funcione bien.");

 				}

 				catch(IOException e){
 					System.out.println("Error de entrada y salida" +e.toString());
 				}
 			}
                }
}
