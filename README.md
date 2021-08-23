- 👋 Hi, I’m @bielbmonteiro
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
bielbmonteiro/bielbmonteiro is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace TesteAccessBasil
{
    class Program
    {
        static void Main(string[] args)
        {
            
            String amostra = "";
            int somaAmostra = 0;
            int media = 0;
            var total = 0;

            Console.WriteLine("Digite a amostra de cada aluno e tira a porcentagen acima da media ");
            amostra = Console.ReadLine();

            if (!amostra.Contains(","))
            {
                Console.WriteLine("Digite a amostra separada por virgula ");
                amostra = Console.ReadLine();
            }

            var lst = amostra.Split(',').ToList();

            foreach (String nota in lst)
            {
                somaAmostra += int.Parse(nota);
            }

            media = somaAmostra / lst.Count;
            
            int  notasAcimaMedia = 0;
            foreach (var nota in lst)
            {
                if (int.Parse(nota) > media)
                {
                    notasAcimaMedia++;
                }
            }
            total = (notasAcimaMedia * 100) / lst.Count;
            Console.ForegroundColor = ConsoleColor.Red; //informa  uma cor
            Console.WriteLine(" A taxa de eficiecia dos alunos acima da média é :" + total);
        }

    }
    
}

