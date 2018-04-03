# ChatbotI18N

Exemplo de chatbot internacionalizado utilizando Microsoft Bot Framework.

Criar um arquivo base (Resource File) para o seu idioma padrão (nesse sample utilizei Inglês - en). Por exemplo: `Strings.resx`
![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/ResourceFile.PNG)

Criar um arquivo para cada idioma da sua aplicação, respeitando a nomenclatura "Strings.culture.resx". Por exemplo: `Strings.es.resx` (Espanhol) | `Strings.fr.resx` (Francês) | `Strings.pt.resx` (Português)

![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/AllResourceFiles.PNG)

Agora adicione as strings equivalentes para cada idioma, elas precisam ter o mesmo nome, altere apenas o valor para cada língua
![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/Strings.PNG)

Com todos os arquivos criados precisamos agora mudar o idioma, nesse exemplo estou pegando o idioma do usuário do chatbot na classe `MessagesController.cs`. Para isso, adicione as referências `System.Threading` e 
`System.Globalization`.

`Thread.CurrentThread.CurrentUICulture = CultureInfo.GetCultureInfo(activity.Locale);` 

Agora execute sua aplicação e abra o emulador, note que o campo **Locale** está em branco, isso indica que não está configurado nenhum idioma para o chatbot. Sendo assim, o retorno será do arquivo `Strings.resx`
![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/Emulator1.PNG)

![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/Emulator2.PNG)

Agora troque o valor do campo **Locale** para **pt-BR** (Português do Brasil) e o chatbot vai retornar os valores do arquivo `Strings.pt.resx` e assim para cada idioma configurado. 
![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/Emulator3.PNG)

![image](https://raw.githubusercontent.com/dfdcastro/ChatbotI18N/master/imgs/Emulator4.PNG)

Caso o idioma selecionado não tenha um arquivo correspondente, o chatbot irá retornar o valor do arquivo padrão `Strings.resx`

Pronto! O chatbot está internacionalizado :)