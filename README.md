# Exemplo-classe-Lazy-do-C#
Exemplo onde explico como ganhar mais performance e memória usando a classe Lazy do C#
```sh
using System;
using System.Text;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            //Criei uma instancia da categoria
            Categoria c = new Categoria();

            //Setei um valor para a propriedade NomeCategoria, mas não setei nada para o usuário
            c.NomeCategoria = "Transporte";

            //Imprimo o valor da propriedade NomeCategoria
            Console.WriteLine("Obtem nome da instancia da Categoria = " + c.NomeCategoria);

            //Verifico se a propriedade UsuarioCadastro foi instanciada através do método IsValueCreated
            Console.WriteLine("UsuarioCadastroInstanciado = " + c.UsuarioCadastro.IsValueCreated);

            //Invoco a propriedade do usuário através do Value
            Console.WriteLine("Resgato o valor da propriedade do usuario");
            Console.WriteLine("Obtem nome da instancia do UsuarioCadastro = " + c.UsuarioCadastro.Value.Nome);

            //Verifico se a propriedade UsuarioCadastro foi instanciada através do método IsValueCreated
            Console.WriteLine("UsuarioCadastroInstanciado = " + c.UsuarioCadastro.IsValueCreated);

            //Fecho o prompt após pressionar uma tecla
            Console.ReadKey();


            StringBuilder sb = new StringBuilder();
            sb.Append("Texto");

        }

        public class Categoria
        {
            public Lazy<Usuario> UsuarioCadastro { get; set; }

            public string NomeCategoria { get; set; }

            public Categoria()
            {
                this.UsuarioCadastro = new Lazy<Usuario>();
            }
        }

        public class Usuario
        {
            public Usuario()
            {
                this.Nome = "Paulo Rogério";
            }
            public string Nome { get; set; }
        }
    }
}
```
