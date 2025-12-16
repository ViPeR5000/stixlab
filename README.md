# STIX 2.1 Helper – Ensino / Teaching Tool

**Autor / Author:** Bruno Cardoso  
**Curso / Course:** C-Academy – PMD#1  
**Repositório / Repository:** https://github.com/brunomac69/stixlab  
**Licença / License:** Open Source  
**Linguagem / Language:** Python 3.x  

---

## 🇵🇹 Descrição (PT)

Esta aplicação gráfica (GUI), desenvolvida com **CustomTkinter (CTk)**, foi criada para apoiar o **ensino e a prática de criação de objetos STIX 2.1**.  
O objetivo é permitir a formandos e analistas compreender facilmente a estrutura dos diferentes tipos de objetos (SDO, SRO e SCO) e gerar JSONs prontos a utilizar — com valores predefinidos didáticos e compatíveis com a norma STIX 2.1.[web:23]

A ferramenta também permite criar **bundles STIX**, adicionar múltiplos objetos e exportar o resultado final para um ficheiro JSON compatível.

---

## 🇵🇹 Funcionalidades Principais

- Interface moderna em *CustomTkinter* (modos Dark, Light e System).
- Suporte para:
  - **SDO (STIX Domain Objects)** – ex: `attack-pattern`, `campaign`, `course-of-action`, `grouping`, `identity`, `indicator`, `infrastructure`, `intrusion-set`, `location`, `malware`, `malware-analysis`, `note`, `observed-data`, `opinion`, `report`, `threat-actor`, `tool`, `vulnerability`.
  - **SRO (STIX Relationship Objects)** – `relationship`, `sighting`.
  - **SCO (STIX Cyber Observable Objects)** – `ipv4-addr`, `ipv6-addr`, `domain-name`, `url`, `email-addr`, `mac-addr`, `mutex`, `file`, `process`, `user-account`, `network-traffic`.
- Geração automática de:
  - `id` com UUIDs válidos (`<type>--<uuid>`).
  - Timestamps no formato ISO 8601 UTC (`created`, `modified`, `first_seen`, `last_seen`, `published`, `valid_from`, `first_observed`, `last_observed`, etc.).
  - Campos opcionais com listas ilustrativas (`aliases`, `kill_chain_phases`, `labels`, `malware_types`, `tool_types`, `threat_actor_types`, etc.).
- Criação e gestão de **bundles STIX 2.1**:
  - Criar novo bundle vazio.
  - Adicionar objetos STIX ao bundle.
  - Visualizar o bundle atual em formato JSON.
  - Exportar o bundle para ficheiro `.json`.
- Código facilmente extensível para incluir novos tipos de objetos STIX.

---

## 🇵🇹 Pré-requisitos

- Python 3.10 ou superior.
- Dependências:
pip install customtkinter 

ou 

pip install -r requirements.txt

text
As restantes (`uuid`, `json`, `datetime`, `tkinter`) fazem parte da biblioteca padrão do Python.

---

## 🇵🇹 Como usar

1. Clonar o repositório:
git clone https://github.com/brunomac69/stixlab.git
cd stixlab

text
2. Certificar que o script (por exemplo) se chama:
main.py

text
ou ajustar o nome no comando seguinte.
3. Executar a aplicação:
python main.py

text
4. Na interface:
- Selecionar **Categoria** (SDO, SRO ou SCO).
- Selecionar o **Objeto STIX** na segunda combobox.
- O painel da esquerda mostra o **JSON completo** (campos obrigatórios + opcionais) pronto a copiar.
- O painel da direita mostra apenas a **lista de campos opcionais** para referência.
5. Botões inferiores:
- **Criar Bundle (novo):** inicia um bundle STIX vazio.
- **Adicionar ao Bundle:** adiciona o JSON atual ao bundle.
- **Ver Bundle:** abre uma nova janela com o bundle em JSON.
- **Exportar Bundle JSON:** guarda o bundle num ficheiro `.json`.

---

## 🇵🇹 Exemplo de objeto “malware”

Ao escolher `SDO (Domain Object)` → `malware`, é gerado um objeto semelhante a:

{
"type": "malware",
"spec_version": "2.1",
"id": "malware--<uuid>",
"created": "2025-12-16T20:51:00Z",
"modified": "2025-12-16T20:51:00Z",
"name": "Nome do objeto",
"is_family": false,
"description": "",
"malware_types": [],
"aliases": [],
"first_seen": "2025-12-16T20:51:00Z",
"last_seen": "2025-12-16T20:51:00Z",
"capabilities": [],
"confidence": 50,
"labels": ["espionage", "ransomware", "etc..."]
}

text

---


## 🇬🇧 Description (EN)

This GUI application, built with **CustomTkinter (CTk)**, is designed to support **teaching and practicing the creation of STIX 2.1 objects**.  
It helps students and analysts understand the structure of different object types (SDO, SRO and SCO) and generate ready-to-use JSON, with educational default values aligned with the STIX 2.1 specification.[web:23]

The tool also allows creating **STIX bundles**, adding multiple objects, and exporting the final result to a compatible JSON file.

---

## 🇬🇧 Main Features

- Modern *CustomTkinter* interface (Dark, Light and System themes).
- Support for:
  - **SDO (STIX Domain Objects)** – e.g. `attack-pattern`, `campaign`, `course-of-action`, `grouping`, `identity`, `indicator`, `infrastructure`, `intrusion-set`, `location`, `malware`, `malware-analysis`, `note`, `observed-data`, `opinion`, `report`, `threat-actor`, `tool`, `vulnerability`.
  - **SRO (STIX Relationship Objects)** – `relationship`, `sighting`.
  - **SCO (STIX Cyber Observable Objects)** – `ipv4-addr`, `ipv6-addr`, `domain-name`, `url`, `email-addr`, `mac-addr`, `mutex`, `file`, `process`, `user-account`, `network-traffic`.
- Automatic generation of:
  - `id` fields with valid UUIDs (`<type>--<uuid>`).
  - ISO 8601 UTC timestamps (`created`, `modified`, `first_seen`, `last_seen`, `published`, `valid_from`, `first_observed`, `last_observed`, etc.).
  - Optional fields with illustrative lists (`aliases`, `kill_chain_phases`, `labels`, `malware_types`, `tool_types`, `threat_actor_types`, etc.).
- Creation and management of **STIX 2.1 bundles**:
  - Create new empty bundle.
  - Add STIX objects to the bundle.
  - View current bundle as JSON.
  - Export bundle to `.json` file.
- Easily extensible code base to add new STIX object types.

---

## 🇬🇧 Requirements

- Python 3.10+
- Dependencies:
pip install customtkinter

text

---

## 🇬🇧 How to Run

1. Clone the repository:
git clone https://github.com/brunomac69/stixlab.git
cd stixlab

text
2. Ensure the script name matches:
main.py

text
or update the command accordingly.
3. Run the app:
python main.py

text
4. Use the GUI to:
- Select **Category** (SDO, SRO, SCO).
- Select **STIX Object** in the second combobox.
- Left panel: full JSON (mandatory + optional fields) ready to copy.
- Right panel: list of optional properties for reference.
5. Use the bottom buttons to:
- Create new bundle.
- Add current object to the bundle.
- View current bundle.
- Export bundle to JSON.

---

## 📜 Licença / License

Este projeto é **open-source** e pode ser reutilizado para fins de ensino e aprendizagem, desde que seja mencionada a autoria original.  
This project is **open-source** and may be reused for teaching and learning purposes, provided original authorship is credited.

---

## 👨‍🏫 Créditos / Credits

**Bruno Cardoso + LLM :)**  
C-Academy | Curso PMD#1  

- LinkedIn: https://www.linkedin.com/in/brunocardoso-cybersecurity/  
- GitHub: https://github.com/brunomac69