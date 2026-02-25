# 📚 PRISMA - Plataforma de Aprendizagem Adaptativa

> **Trabalho de Conclusão de Curso (TCC)**
> [cite_start]**Cliente:** Andreia Frazão Sano (Psicopedagoga) [cite: 30, 77]

## 🎯 Sobre o Projeto

[cite_start]O PRISMA é um sistema de apoio ao aprendizado desenvolvido para solucionar o desafio da heterogeneidade nas salas de aula[cite: 36, 74]. [cite_start]O projeto visa automatizar a personalização do ensino, permitindo que professores disponibilizem materiais didáticos e que os alunos recebam versões adaptadas desse conteúdo[cite: 80]. 

[cite_start]Através da integração com Inteligência Artificial (LLM), o sistema transforma materiais estáticos (arquivos PDF ou Word) em roteiros de estudo personalizados, com base no perfil psicológico de aprendizado de cada aluno, guiado pela metodologia **VARK** (Visual, Auditivo, Leitura/Escrita e Cinestésico)[cite: 80, 83, 85].

## ✨ Funcionalidades (Escopo do MVP)

* [cite_start]**Identificação de Perfil:** Teste interativo (Questionário VARK) no primeiro acesso do aluno para mapear seu estilo de aprendizado[cite: 91, 103].
* [cite_start]**Gestão de Turmas e Upload:** Área restrita para o professor realizar o upload de materiais (PDF, DOCX, TXT) vinculados às suas turmas[cite: 94, 95, 107].
* [cite_start]**Extração e Processamento:** Leitura automatizada do arquivo e extração do texto bruto utilizando a biblioteca `PyPDF2`[cite: 25, 98, 108].
* [cite_start]**Adaptação por Inteligência Artificial:** Orquestração de prompts baseados no perfil do aluno (ex: uso de metáforas visuais para alunos com perfil "Visual") para gerar uma explicação didática e humanizada[cite: 109].
* [cite_start]**Sistema de Cache e Otimização:** Armazenamento das adaptações geradas pela IA no banco de dados para evitar chamadas redundantes à API e acelerar o tempo de resposta[cite: 115, 116, 195].

## 🛠️ Tecnologias Utilizadas

[cite_start]A stack do projeto foi escolhida visando alta performance e facilidade de manutenção[cite: 120, 121, 122]:

* [cite_start]**Frontend:** Vue.js 3 com biblioteca de componentes visuais (Vuetify ou Tailwind CSS)[cite: 125, 126].
* [cite_start]**Backend:** Python 3.12+ utilizando o framework FastAPI[cite: 121, 124].
* [cite_start]**Inteligência Artificial:** LangChain, LanGgraph e integração com LLMs (OpenAI API, Google Gemini ou Amazon Bedrock)[cite: 124, 128].
* [cite_start]**Banco de Dados:** PostgreSQL ou SQLite (armazenamento persistente de dados cadastrais, textos originais extraídos e textos adaptados em cache)[cite: 127].
* [cite_start]**Infraestrutura:** Docker para padronização do ambiente de desenvolvimento[cite: 130].
* [cite_start]**Controle de Versão:** Git e GitHub[cite: 129].

## 🏗️ Arquitetura e Fluxo de Dados

1. [cite_start]O **Professor** faz o upload de um PDF através da interface Web[cite: 14, 21].
2. [cite_start]O **Backend (FastAPI)** recebe o arquivo e utiliza o `Service: PyPDF2` para extrair as strings de texto[cite: 17, 21, 25].
3. [cite_start]O **Orquestrador** verifica se já existe uma adaptação para o perfil do aluno no banco de dados (`Cache Existe?`)[cite: 17].
4. [cite_start]Caso não exista, o Orquestrador monta o prompt instrucional e envia o contexto do material para a LLM[cite: 17, 21].
5. [cite_start]O **Aluno** consome o conteúdo final adaptado[cite: 14, 21].

## 👥 Equipe de Desenvolvimento

* [cite_start]Luiz Felipe Siqueira de Souza (6324548) [cite: 8, 31, 76, 147]
* [cite_start]Leonardo Frazão Sano (6324073) [cite: 8, 31, 32, 76, 147]
* [cite_start]Natan Borges Leme (6324696) [cite: 8, 32, 76, 147]
* [cite_start]Vitor Pinheiro Guimarães (6324680) [cite: 8, 32, 76, 147]