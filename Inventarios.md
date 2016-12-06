# Inventaros

public class Cantidad {
	
	public int max;
    protected Object dret;
    public Object c[];
    public int fre = -1;
    public int fin = -1;
 
    public Cantidad()
     {
        max=20;
        c=new Object [max];
     }
 
    public Cantidad(int n)
       { max=n;
        c=new Object [max];
       } 
 
    public boolean colallena(int fin,int max)
    {
      boolean llena;
      if (fin==max-1)
        llena=true;
        else
          llena=false;
      return llena;
     }
 
    public boolean colavacia(int fre)
    {
      boolean vacia;
      if (fre==-1)
        vacia=true;
        else
          vacia=false;
      return vacia;
     }   
 
    public boolean inscola(Object dato) //insertar
     {
        if (fin==max-1)
           return false;
        fin++;
        c[fin] = dato;
        if (fin==0)
           fre=0;
        return true;
     }
 
    public boolean retcola() //retirar
      {
        if (fre ==-1)
           return false;
        dret=c[fre];
        if (fre==fin)
          {
            fre=-1;
            fin=-1;
          }
         else
           fre++;
        return true;
      }

}

public class Articulo {
	
	public int max;
    protected Object dret;
    public Object a[];
    public int fre = -1;
    public int fin = -1;
 
    public Articulo()
     {
        max=20;
        a=new Object [max];
     }
 
    public Articulo(int n)
       { max=n;
        a=new Object [max];
       } 
 
    public boolean colallena(int fin,int max)
    {
      boolean llena;
      if (fin==max-1)
        llena=true;
        else
          llena=false;
      return llena;
     }
 
    public boolean colavacia(int fre)
    {
      boolean vacia;
      if (fre==-1)
        vacia=true;
        else
          vacia=false;
      return vacia;
     }   
 
    public boolean inscola(Object dato) //insertar
     {
        if (fin==max-1)
           return false;
        fin++;
        a[fin] = dato;
        if (fin==0)
           fre=0;
        return true;
     }
 
    public boolean retcola() //retirar
      {
        if (fre ==-1)
           return false;
        dret=a[fre];
        if (fre==fin)
          {
            fre=-1;
            fin=-1;
          }
         else
           fre++;
        return true;
      }

}

public class Existencia {
	
	public int max;
    protected Object dret;
    public Object e[];
    public int fre = -1;
    public int fin = -1;
 
    public Existencia()
     {
        max=20;
        e=new Object [max];
     }
 
    public Existencia(int n)
       { max=n;
        e=new Object [max];
       } 
 
    public boolean colallena(int fin,int max)
    {
      boolean llena;
      if (fin==max-1)
        llena=true;
        else
          llena=false;
      return llena;
     }
 
    public boolean colavacia(int fre)
    {
      boolean vacia;
      if (fre==-1)
        vacia=true;
        else
          vacia=false;
      return vacia;
     }   
 
    public boolean inscola(Object dato) //insertar
     {
        if (fin==max-1)
           return false;
        fin++;
        e[fin] = dato;
        if (fin==0)
           fre=0;
        return true;
     }
 
    public boolean retcola() //retirar
      {
        if (fre ==-1)
           return false;
        dret=e[fre];
        if (fre==fin)
          {
            fre=-1;
            fin=-1;
          }
         else
           fre++;
        return true;
      }

}

import java.util.*;

public class Main {
	
	    public static void main( String args[] ){
	       Scanner leer = new Scanner(System.in);
	 
	       Cantidad c = new Cantidad();
	       Articulo a = new Articulo();
	       Existencia e = new Existencia();
	 
	       int op;
	       int num, exist;
	       String art;
	 
	       do{
	          menu();
	          op = leer.nextInt();
	 
	          switch(op){
	              case 1:
	                     System.out.println( "Caja numero: : " );
	                     num = leer.nextInt();
	                     leer.nextLine();
	                     System.out.println( "Nombre:: " );
	                     art = leer.nextLine();
	                     System.out.println( "Peso:" );
	                     exist = leer.nextInt();
	                     if(c.inscola(num) && a.inscola(art) && e.inscola(exist)){
	                        System.out.println( "La caja n°: "+num+" de "+art+ " con "+exist+" kg se ha registrado." );

	                        System.out.println();
	                     }
	                     else{
	                          System.out.println( "Cola llena" );
	                     }
	                     break;
	              case 2:
	                    if(c.retcola()&&a.retcola()&&e.retcola()){
	                       System.out.println( "El dato retirado fue: "+c.dret+a.dret+e.dret );
	                    }
	                    else{
	                        System.out.println( "Cola vacia" );
	                    }
	                    break;
	              case 3:
	                    if(c.fre==-1 && c.fin==-1){
	                       System.out.println( "Cola vacia" );
	                    }
	                    else{
	                         System.out.println("Estado de inventarios: " );
	                         System.out.println("Caja\t Articulo\t Kilos: " );
	                         for(int i=c.fre; i<=c.fin; i++){
	                            System.out.print(c.c[i]+"\t "+ a.a[i]+ "\t "+ e.e[i]);
	                          
	                            
	                         }
	                         break;
	                    }
	          }
	       }
	       while(op != 4);
	    }
	 
	    public static void menu(){
	       System.out.println( "\n\nMenu para colas \n" );
	       System.out.println( "1.- Insertar" );
	       System.out.println( "2.- Retirar" );
	       System.out.println( "3.- Estado" );
	       System.out.println( "4.- Fin" );
	       System.out.println( "\n Selecciona" );
	    }
	}
