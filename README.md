# practica6consolausing System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Threading;

namespace practica61
{
    class Program
    {
        static void Main(string[] args)
        {
            Thread p1 = new Thread(cargarImagenes);
            Thread p2 = new Thread(registrarDatos);
            p1.Start("IMAGENES");
            p2.Start("REGISTRO");
            while (p1.IsAlive || p2.IsAlive);
            Console.WriteLine("PROCESO TERMINADO");

        }

        public static void cargarImagenes(object nombre) 
        { 
            for (int i = 0; 1 < 10; i++)
            {
                Console.WriteLine ( nombre + " -> CARGANDO IMAGENES..");
                Thread.Sleep(200);

            }
            Console.WriteLine(nombre + " -> CARGA DE IMAGENES COMPLETA");
        }
        public static void registrarDatos(object nombre)
        {
            for (int i = 0; 1 < 10; i++)
            {
                Console.WriteLine(nombre + " -> REGISTRANDO DATOS");
                Thread.Sleep(500);

            }
            Console.WriteLine(nombre + " -> CARGA COMPLETA");



        }

    }
}

consola
