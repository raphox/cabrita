<p align="center" width="100%">
<img src="assets/cabrita.png" alt="Cabrita" style="width: 20%; min-width: 300px; display: block; margin: auto;">
</p>

# Cabrita: Uma instrução finetuned em português para LLaMA

Este repositório tem como objetivo compartilhar todos os passos e recursos que usamos para realizar finetune na nossa versão do LLaMA.

Este modelo foi projetado apenas para uso em pesquisa, ou seja, não pode ser usado para fins comerciais ou de entretenimento.


## Referências

> Se eu vi mais longe foi por estar de pé sobre ombros de gigantes.
> -- <cite>Isaac Newton</cite>

Começamos esta seção com essa citação porque tudo o que fizemos foi possível apenas devido à forte comunidade e trabalhos que outras pessoas e grupos fizeram. Para o nosso trabalho, confiamos principalmente nos trabalhos desenvolvidos por: [LLaMA](https://ai.facebook.com/blog/large-language-model-llama-meta-ai/), [Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca), [Alpaca Lora](https://github.com/tloen/alpaca-lora), [ChatGPT](https://openai.com/blog/chatgpt) e [Hugging Face](https://huggingface.co/). Então, obrigado a todos pelo excelente trabalho e por abrir isso para o mundo!


## Dados

Traduzimos o [alpaca_data.json](https://github.com/tatsu-lab/stanford_alpaca/blob/main/alpaca_data.json) para português usando o ChatGPT. Mesmo que essa tradução não tenha sido a melhor, o trade-off entre custos e resultados foi aceitável. Pagamos cerca de US$ 8,00 para traduzir o conjunto de dados completo para o português.

Se você quiser saber mais sobre como o conjunto de dados foi construído, vá para: [Stanford Alpaca](https://github.com/tatsu-lab/stanford_alpaca).


## Finetuning

Para realizar o finetuned do modelo LLaMA, usamos o código disponível no [Alpaca Lora](https://github.com/tloen/alpaca-lora), que fornece código para finetunar o modelo LLaMA usando PEFT da Hugging Face. Com isso, pudemos executar nosso passo de finetuning usando 1 A100 no Colab em cima do LLaMA-7B. Treinamos por 1 hora e achamos os resultados incríveis com apenas esse tempo. O notebook que usamos está disponível [aqui](notebooks/train_lora.ipynb)..


## Exemplo de resultados

Stanford Alpaca:
```
Instruction: Invente uma desculpa criativa pra dizer que não preciso ir à festa.
Response: Eu preciso se concentrar em trabalho importante para mim, por isso eu não posso ir à festa.
```

Cabrita:
```
Instrução: Invente uma desculpa criativa pra dizer que não preciso ir à festa.
Resposta: "Eu preciso ficar em casa para cuidar dos meus animais de estimação."
```


Stanford Alpaca:
```
Instruction: Como posso começar a carreira como cientista de dados? Escreva na forma de lista.
Response:
1. Comece por se especializar em um campo específico, como big data, computação, bioinformática ou estatística.
2. Obtivere um diploma em um programa de graduação relacionado a ciência de dados, como informática, matemática ou estatística.
3. Aquisite experiência prática através de internships ou projetos em empresas ou instituições.
4. Ameize sua resumo e currículo com resultados relevantes e experiência em trabalho relacionado.
5. Leia artigos, livros e atualizações sobre ciência de dados.
6. Crie um portfólio com projetos e experimentos que tenha realizado.
7. Receba um certificado de qualificação em alguma área de ciência de dados.
8. Tente obter contato com profissionais da área para conversar sobre oportunidades de emprego.
9. Acesse redes sociais, como LinkedIn, para encontrar empregos e conexões.
10. Continui sua formação atualizando-se com tecnologias e ferramentas de ciência de dados.
```

Cabrita:
```
Instrução: Como posso começar a carreira como cientista de dados? Escreva na forma de lista.
Resposta: 
1. Obtenha um mestrado em ciência de dados ou engenharia de dados.
2. Encontre um emprego como cientista de dados ou engenheiro de dados.
3. Conheça as principais ferramentas de análise de dados, como Python, R e SQL.
4. Conheça as principais técnicas de análise de dados, como regressão linear, regressão logística e análise de clustering.
5. Conheça as principais abordagens de análise de dados, como análise exploratória, análise de associação e análise de regressão.
6. Conheça as principais ferramentas de visualização de dados, como Tableau, QlikView e Power BI.
7. Conheça as principais abordagens de análise de dados, como análise de associação, análise de regressão e análise exploratória.
```

You can test it using the eval notebook [here](notebooks/cabrita-lora.ipynb).

## Próximos passos

- Criar um conjunto de dados em português melhor
- Avaliar a toxicidade
- Finetune de modelos grandes


## Autores

- [piEsposito](https://github.com/piEsposito)
- [pedrogengo](https://github.com/pedrogengo)
