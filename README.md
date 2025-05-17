# procurando_vaga
Repositório do projeto 'Procurando Vaga', que concorre na Imersão de IA - Alura &amp; Google

![license - MIT](https://img.shields.io/badge/license-MIT-green)
[![site - prazocerto.me](https://img.shields.io/badge/site-prazocerto.me-230023)](https://prazocerto.me)
[![linkedin - @marioluciofjr](https://img.shields.io/badge/linkedin-marioluciofjr-blue)](https://linkedin.com/in/marioluciofjr)

## Índice

* [Introdução](#introdução)
* [Estrutura do projeto](#estrutura-do-projeto)
* [Tecnologias utilizadas](#tecnologias-utilizadas)
* [Requisitos](#requisitos)
* [Como obter a API KEY no Google AI Studio](#como-obter-a-api-key-no-google-ai-studio)
* [Como configurar a API KEY no Google Colab](#como-configurar-a-api-key-no-google-colab)
* [Como executar](#como-executar)
* [Links úteis](#links-úteis)
* [Contribuições](#contribuições)
* [Licença](#licença)
* [Contato](#contato)

## Introdução

Este projeto utiliza um sistema de múltiplos agentes para auxiliar usuários na busca por vagas de emprego na área de tecnologia. O usuário insere suas informações e preferências de carreira, e quatro agentes especializados entram em ação: Carlos Acha (recrutador), Sofia Leme (mentora de carreira), Laura Code (professora tech) e Hash Tag (especialista em LinkedIn). Cada agente contribui com sua expertise, desde a busca inicial de vagas até dicas de estudo, soft skills, hard skills e otimização do perfil no LinkedIn para aumentar as chances de sucesso da pessoa candidata.

## Estrutura do projeto

A ideia desse projeto surgiu na Imersão IA - Alura & Google, a fim de participar da premiação dos melhores projetos. Levando em consideração que as aulas 4 e 5 da Imersão mostraram que é possível fazer as pesquisas no Google com os modelos do Gemini, logo pensei "Então pode ser uma boa para procurar oportunidades de emprego". 

Acredito que esse projeto pode ser útil para todas as pessoas na comunidade do Discord, principalmente aquelas que desejam se recolocar no mercado de trabalho ou mesmo migrar para uma área tech. Eu poderia ter abrangido para vagas diversas, mas foi uma escolha editoral focar somente em vagas de áreas tech, fazendo sentido com o ambiente em si da Alura, tanto é que o dropbox utilizado no código tem as opções de áreas disponíveis no site da Alura.

Fiz duas versões de código em python. A primeira é mais simples e que faz total sentido com a aula 5, rodando exclusivamente no Google Colab com a api_key do Gemini configurada devidamente no secrets. Já a segunda versão tem a interface da bilioteca Gradio, a fim de tornar a experiência mais inclusiva possível. Ambos os códigos estão devidamente comentados para ajudar em qualquer manutenção ou contribuição de outros devs.

Nos meus testes, o modelo generativo que fez mais sentido (mesmo que leve um certo delay na resposta por conta da cadeia de pensamento) foi o `gemini-2.5-flash-preview-04-17-thinking`. 

Sobre os agentes inteligentes utilizados nos códigos, segue a explicação de cada um e o que faz: 

### Carlos Acha - recrutador de uma agência de emprego

Carlos Acha é um agente recrutador de 30 anos, especialista em encontrar vagas de emprego, principalmente na área de tecnologia. Sua função no código é buscar na internet 10 oportunidades de trabalho que correspondam ao perfil e às informações fornecidas pelo usuário (área, experiência, formação, cursos e localidade). Como resultado, Carlos entrega uma lista detalhada dessas 10 vagas, incluindo nome da empresa, localização, cargo, salário (se disponível), uma breve descrição e o link direto para a vaga, priorizando sites confiáveis de emprego.

> [!IMPORTANT]
> Sempre verifique se as informações estão corretas, pois como está escrito no rodapé do próprio Gemini "O Gemini pode cometer erros. Por isso, é bom checar as respostas"

### Sofia Leme - mentora de carreira

Sofia Leme é uma mentora de carreira experiente de 48 anos, ex-Headhunter, com uma abordagem séria e empática. No código, ela analisa as 10 vagas encontradas por Carlos Acha e seleciona as 3 mais adequadas para o usuário, justificando cada escolha. Sofia também fornece 5 dicas de soft skills cruciais para o candidato se destacar e pesquisa 3 notícias ou assuntos relevantes para manter o usuário informado sobre o mercado das vagas selecionadas, auxiliando no direcionamento profissional.

### Laura Code - professora de cursos de áreas tech

Laura Code é uma professora de tecnologia de 37 anos, didática e inspirada pela Alura, focada em carreiras como Programação e IA. Sua função é analisar as 3 vagas selecionadas por Sofia e fornecer dicas de estudo para o usuário se preparar. Laura também lista 5 hard skills essenciais, cria um checklist de 5 passos para desenvolver uma carreira em "T" (baseado no Tech Guide da Alura) e recomenda 3 cursos específicos da Alura alinhados com a área de interesse do usuário.

### Hash Tag - estrategista digital, especialista em LinkedIn

Hash Tag é uma estrategista digital de 26 anos, especialista em LinkedIn e Top Voice em tecnologia. No projeto, ela orienta o usuário a otimizar seu perfil no LinkedIn para as 3 vagas em foco, detalhando seções como foto, headline e experiências. Hash Tag também sugere 3 temas de posts para aumentar a visibilidade do usuário na rede, indica 5 perfis influentes para seguir, visando networking e melhora do SSI (Social Selling Index), e finaliza com uma mensagem de encorajamento.

> [!NOTE]
> Sim, os nomes foram propositais para fazer pequenas referências ao que cada um faz. O do Carlos é bem óbvio, pois tem o sobrenome 'Acha', levando em consideração que ele busca vagas. Escolhi Sofia porque significa sabedoria e o sobrenome Leme na intenção dela saber conduzir o leme e evitar águas turbulentas, ajudando seus mentorados (cito algo desse tipo no prompt inclusive). Já a Laura é um anagrama de Alura, sendo que o sobrenome Code é código em inglês. Por fim, a Hash Tag é mais óbvia ainda, pois vem de hashtag, recurso muito conhecido em redes sociais.

## Tecnologias utilizadas

<div>
  <img align="center" height="60" width="80" src="https://github.com/user-attachments/assets/63e3b960-3dc5-48fc-a300-b3104430235f" />&nbsp;&nbsp;&nbsp
  <img align="center" height="60" width="80" src="https://github.com/user-attachments/assets/31ed57e7-f4b7-4d86-9373-668a38f8db17" />&nbsp;&nbsp;&nbsp  
  <img align="center" height="60" width="80" src="https://upload.wikimedia.org/wikipedia/commons/d/d0/Google_Colaboratory_SVG_Logo.svg" />&nbsp;&nbsp;&nbsp    
  <img align="center" height="60" width="80" src="https://github.com/user-attachments/assets/0324b2d2-c9f4-4c2e-ba62-703a7f346de6" />&nbsp;&nbsp;&nbsp
  <img align="center" height="60" width="80" src="https://github.com/user-attachments/assets/76e7aca0-5321-4238-9742-164c20af5b4a" />&nbsp;&nbsp;&nbsp
  <img align="center" height="60" width="80" src="https://github.com/user-attachments/assets/7897cf9f-0349-4e05-afe8-65554fc49ecc" />&nbsp;&nbsp;&nbsp
    
</div>

## Requisitos

Para utilizar este projeto, você precisa de:

- **Conta Google**: Necessária para acessar o Google AI Studio e o Google Colab
- **Chave de API do Google AI Studio (Gemini API)**: Instruções para obtenção abaixo

> [!IMPORTANT]
> O código [`procurando_vaga.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga.ipynb) está configurado para ser executado no Google Colab, que fornece todos os recursos computacionais necessários gratuitamente.\
> Já o código [`procurando_vaga_gradio.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga_gradio.ipynb) está configurado para ser utilizado em uma interface Gradio. Explicarei mais abaixo o procedimento.

## Como obter a API KEY no Google AI Studio

Para utilizar este código, você precisará de uma chave de API do Google Gemini:

1. Acesse o [Google AI Studio](https://ai.dev/app/apikey)
2. Faça login com sua conta Google
3. Clique no botão "Criar chave de API"
4. Aceite os termos de serviço, se solicitado
5. Copie a chave gerada e guarde-a em local seguro

> [!IMPORTANT]
> Atualmente, o Google AI Studio oferece um uso gratuito da API para testes. Sobre demais detalhes da API do Gemini, leia a [documentação oficial](https://ai.google.dev/gemini-api/docs/pricing?hl=pt-br#:~:text=O%20uso%20do%20Google%20AI,em%20todos%20os%20pa%C3%ADses%20dispon%C3%ADveis).

## Como configurar a API KEY no Google Colab

Para utilizar sua chave API no Google Colab de forma segura:

1. Abra seu notebook no Google Colab
2. Na barra lateral esquerda, clique no ícone 🔑 (Secrets)
3. Clique em "+ Adicionar novo secret"
4. No campo "Nome", digite `senha`
5. No campo "Valor", cole sua chave API do Google AI Studio

> [!TIP]
> O código [`procurando_vaga.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga.ipynb) está configurado para acessar a chave por meio de `userdata.get('senha')`. Se preferir usar outro nome, modifique esta célula no código: 

```python
# Configurando a API

os.environ['GOOGLE_API_KEY'] = userdata.get('senha')
os.environ["GOOGLE_GENAI_USE_VERTEXAI"] = "False"

print("API_KEY configurada")
  ```

## Como executar

Abaixo você terá um checklist básico para executar o projeto tanto no Google Colab quanto no Gradio, sendo que o atalho para executar as células `CTRL` + `ENTER`

### Versão [`procurando_vaga.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga.ipynb)

- [ ] Obter a API_KEY no Google AI Studio
- [ ] Clicar no botão ![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg) dentro do arquivo [`procurando_vaga.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga.ipynb)
- [ ] Configurar a API_KEY em 'Secrets' no Google Colab.
- [ ] Executar a 1ª célula do código (Instalação do ADK)
- [ ] Executar a 2ª célula do código (Importação dos pacotes necessários)
- [ ] Executar a 3ª célula do código (Configurando a API)
- [ ] Executar a 4ª célula do código (Função call_agent)
- [ ] Executar a 5ª célula do código (Função to_markdown)
- [ ] Executar a 6ª célula do código (Definindo o modelo Gemini)
- [ ] Executar a 7ª célula do código (Agente 1)
- [ ] Executar a 8ª célula do código (Agente 2)
- [ ] Executar a 9ª célula do código (Agente 3)
- [ ] Executar a 10ª célula do código (Agente 4)
- [ ] Executar a 11ª célula do código (Lógica da saída)

### Versão [`procurando_vaga_gradio.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga_gradio.ipynb)

- [ ] Obter a API_KEY no Google AI Studio
- [ ] Clicar no botão ![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg) dentro do arquivo [`procurando_vaga_gradio.ipynb`](https://github.com/marioluciofjr/procurando_vaga/blob/main/procurando_vaga_gradio.ipynb)
- [ ] Executar a 1ª célula do código (Instalação do ADK)
- [ ] Executar a 2ª célula do código (Importação dos pacotes necessários)
- [ ] Executar a 3ª célula do código (Configurando para não usar VERTEX AI)
- [ ] Executar a 4ª célula do código (Função call_agent)
- [ ] Executar a 5ª célula do código (Definindo o modelo Gemini)
- [ ] Executar a 6ª célula do código (Agente 1)
- [ ] Executar a 7ª célula do código (Agente 2)
- [ ] Executar a 8ª célula do código (Agente 3)
- [ ] Executar a 9ª célula do código (Agente 4)
- [ ] Executar a 10ª célula do código (Lógica da saída)
- [ ] Executar a 11ª célula do código (Interface do Gradio)

> [!IMPORTANT]
> Na Interface do Gradio é que você insere a api_key para funcionar o código
> 
> ![Image](https://github.com/user-attachments/assets/e281a2f4-417e-42ba-9fe3-880c6e67de1e)
>
> Ao executar a 11ª célula, você vai perceber que a interface aparece logo embaixo, mas você pode clicar no link gerado ma parte "Running on public URL"
> 
> ![Image](https://github.com/user-attachments/assets/6429ac15-0f9d-4459-ab89-277955411a47)

## Links úteis

* [Documentação oficial do ADK (Agent Development Kit)](https://google.github.io/adk-docs/) - Tudo que você precisa saber sobre o ADK do Google;
* [O que é vibe coding?](https://medium.com/@niall.mcnulty/vibe-coding-b79a6d3f0caa) - Explica como programar descrevendo o que você quer em linguagem natural;
* [O que são agentes de IA?](https://www.ibm.com/br-pt/think/topics/ai-agents) - Explicação da IBM sobre agentes inteligentes de IA;
* [Documentação da biblioteca Gradio](https://www.gradio.app/docs) - tudo sobre o Gradio e como criar uma interface a partir de python;
* [O que é uma API?](https://www.alura.com.br/artigos/api) - Guia da Alura sobre APIs;
* [Tudo sobre o Secrets do Google Colab](https://medium.com/@parthdasawant/how-to-use-secrets-in-google-colab-450c38e3ec75) - Tutorial completo sobre armazenamento seguro no Google Colab;
* [Curso Engenharia de Prompt: criando prompts eficazes para IA Generativa](https://cursos.alura.com.br/course/engenharia-prompt-criando-prompts-eficazes-ia-generativa) - curso do instrutor Fabrício Carraro;
* [Hugging Face: explorando e aplicando soluções com modelos de IA](https://cursos.alura.com.br/course/hugging-face-explorando-aplicando-solucoes-modelos-ia) - curso da instrutora Valquíria Alencar;

## Contribuições

Contribuições são bem-vindas! Se você tem ideias para melhorar este projeto, sinta-se à vontade para fazer um fork do repositório.

## Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [**`LICENSE`**](https://github.com/marioluciofjr/procurando_vaga/blob/main/LICENSE) para detalhes.

## Contato
    
Mário Lúcio - Prazo Certo®
<div>  	
  <a href="https://www.linkedin.com/in/marioluciofjr" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a> 
  <a href = "mailto:marioluciofjr@gmail.com" target="_blank"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white"></a>
  <a href="https://prazocerto.me/contato" target="_blank"><img src="https://img.shields.io/badge/prazocerto.me/contato-230023?style=for-the-badge&logo=wordpress&logoColor=white"></a>
</div> 
