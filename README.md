# 📚 PRISMA - Plataforma de Aprendizagem Adaptativa

> **Trabalho de Conclusão de Curso (TCC)**
> **Cliente:** Andreia Frazão Sano (Psicopedagoga) [cite: 30, 77]

## 🎯 Sobre o Projeto

O PRISMA é um sistema de apoio ao aprendizado desenvolvido para solucionar o desafio da heterogeneidade nas salas de aula. O projeto visa automatizar a personalização do ensino, permitindo que professores disponibilizem materiais didáticos e que os alunos recebam versões adaptadas desse conteúdo. 

Através da integração com Inteligência Artificial (LLM), o sistema transforma materiais estáticos (arquivos PDF ou Word) em roteiros de estudo personalizados, com base no perfil psicológico de aprendizado de cada aluno, guiado pela metodologia **VARK** (Visual, Auditivo, Leitura/Escrita e Cinestésico).

## ✨ Funcionalidades (Escopo do MVP)

* **Identificação de Perfil:** Teste interativo (Questionário VARK) no primeiro acesso do aluno para mapear seu estilo de aprendizado.
* **Gestão de Turmas e Upload:** Área restrita para o professor realizar o upload de materiais (PDF, DOCX, TXT) vinculados às suas turmas.
* **Extração e Processamento:** Leitura automatizada do arquivo e extração do texto bruto utilizando a biblioteca `PyPDF2`.
* **Adaptação por Inteligência Artificial:** Orquestração de prompts baseados no perfil do aluno (ex: uso de metáforas visuais para alunos com perfil "Visual") para gerar uma explicação didática e humanizada.
* **Sistema de Cache e Otimização:** Armazenamento das adaptações geradas pela IA no banco de dados para evitar chamadas redundantes à API e acelerar o tempo de resposta[cite: 115, 116, 195].

## 🛠️ Tecnologias Utilizadas

A stack do projeto foi escolhida visando alta performance e facilidade de manutenção:

* **Frontend:** Vue.js 3 com biblioteca de componentes visuais (Vuetify ou Tailwind CSS).
* **Backend:** Python 3.12+ utilizando o framework FastAPI.
* **Inteligência Artificial:** LangChain, LanGgraph e integração com LLMs (OpenAI API, Google Gemini ou Amazon Bedrock).
* **Banco de Dados:** PostgreSQL ou SQLite (armazenamento persistente de dados cadastrais, textos originais extraídos e textos adaptados em cache).
* **Infraestrutura:** Docker para padronização do ambiente de desenvolvimento.
* **Controle de Versão:** Git e GitHub.

## 🏗️ Arquitetura e Fluxo de Dados

1. O **Professor** faz o upload de um PDF através da interface Web.
2. O **Backend (FastAPI)** recebe o arquivo e utiliza o `Service: PyPDF2` para extrair as strings de texto.
3. O **Orquestrador** verifica se já existe uma adaptação para o perfil do aluno no banco de dados (`Cache Existe?`).
4. Caso não exista, o Orquestrador monta o prompt instrucional e envia o contexto do material para a LLM.
5. O **Aluno** consome o conteúdo final adaptado.

## 👥 Equipe de Desenvolvimento

* Luiz Felipe Siqueira de Souza (6324548)
* Leonardo Frazão Sano (6324073)
* Natan Borges Leme (6324696)
* Vitor Pinheiro Guimarães (6324680)