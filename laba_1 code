using System.Text.Json;

namespace Laba_1
{
    class Program
    {
        static void Main(string[] args)
        {
            Program program = new Program();
            program.Start();
            Console.ReadKey();
        }
        void Start()
        {
            Console.WriteLine("press Enter to start...\n");
            ConsoleKey key = Console.ReadKey().Key;
                do
                {
                    try
                    {
                    Console.WriteLine("\n\nЯке завдання виконувати?\n\n");
                    int n = int.Parse(Console.ReadLine());
                    Console.WriteLine();
                    if (n == 1) { Task1(); }
                    else if (n == 2) { Task2(); }
                    else if (n == 3) { Task3(); }
                    else Console.WriteLine("\n\nТакого завдання не існує. Ви старалися^^");
                    }
                catch (Exception) { Console.WriteLine("\n\noops..something went wrong..:(\n\n"); }
                }
                while (key == ConsoleKey.Enter);
        }
        void Task1()
        {
            //У списку всі елементи різні. Поміняйте місцями мінімальний і максимальний елемент цього списку.
            int Maximum=0, Minimum=0;
            Random random = new Random();
            int count = random.Next(5,20);
            Console.WriteLine($"count = {count}");
            List<int> List = new List<int>(count);
            while(count > 0)
            {
                List.Add(random.Next(0,20));
                count--;
            }
            Console.WriteLine();
            for(int i = 0; i < List.Count; i++)
            {
                Console.Write(List[i]+"\t");
            }            
            for (int i = 0; i < List.Count; i++)
            {
                if (List[i] == List.Max())
                {
                    Maximum = List[i];
                }
                else if (List[i] == List.Min())
                {
                    Minimum = List[i];
                }
                else continue;
            }
            Console.WriteLine("\n\n\n");
            for (int i = 0; i < List.Count; i++)
            {
                if (List[i] == Maximum) { Console.Write(Minimum+"\t"); }
                else if (List[i] == Minimum) { Console.Write(Maximum+"\t"); }
                else { Console.Write(List[i] +"\t"); }
            }
        }
        void Task2()
        {
            //Відсортувати значення ключів словника по спаданню. Вхідний словник : {'Math':81, 'Physics':83, 'Chemistry':87}. Очікуваний результат: [('Chemistry', 87), ('Physics', 83), ('Math', 81)]
            Dictionary<string, int> dictionary = new Dictionary<string, int>
            {
                {"Math",81},
                {"Physics",83},
                {"Chemistry",87}
            };
            foreach (var key in dictionary)
            {
                Console.WriteLine(key.Key + " -- " + key.Value);
            }
            Console.WriteLine("\n---------------\n");
            var ordered = dictionary.OrderByDescending(x => x.Value).ToDictionary(x => x.Key, x => x.Value);
            string json = JsonSerializer.Serialize(ordered);
            Console.WriteLine(json);
        }
        void Task3()
        {
            //Дана послідовність додатних цілих чисел. Обробляючи тільки непарні числа, отримати послідовність їх строкових уявлень і впорядкувати її в лексикографічному порядку по зростанню. (3)
            //- Select, SelectMany, Where
            int[] numbers = { 2, 47, 457, 2308, 256, 6, 125, 45, 76, 3, 93, 90, 35, 1, 0, 3456, 9076, 7 };
            var oddnumbers = from n in numbers
                             where n % 2 == 1 // 47      457     125     45      3       93      35      1       7
                             orderby n
                             select n;
            foreach (int n in oddnumbers)
                Console.Write(n + "\t");
            Console.WriteLine();
        }
    }
}
