//Cwiczenie_LIFO

using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LIFO_Excersise
{
    class Program
    {
        static void Main(string[] args)
        {
            var stack = new Stos();

            stack.Push(1);
            stack.Push(2);
            stack.Push(3);
            Console.WriteLine(stack.Pop());
            Console.WriteLine(stack.Pop());
            Console.WriteLine(stack.Pop());
        }
    }
}

//Klasa Stos

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LIFO_Excersise
{
    public class Stos
    {
        private List<object> StackLista = new List<object>();

        public void Push(object obj)
        {
            if (obj == null)
                throw new InvalidOperationException("Object(obj) can't be null value");

            StackLista.Add(obj);
        }

        public object Pop()
        {
            if (StackLista.Count == 0)
                throw new Exception("Stack jest pusty");
            var ostatniWpis = StackLista.Count - 1;
            var wynik = StackLista[ostatniWpis];
            StackLista.RemoveAt(ostatniWpis);

            return wynik;
        }

        void Clear()
        {
                StackLista.Clear();
        }
    }
}
