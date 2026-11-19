# 📄 Automação de Padronização de Comprovantes e DARFs

Script em Python desenvolvido para eliminar o trabalho manual de abrir, ler e renomear dezenas de comprovantes de pagamento e guias fiscais (DARF) em PDF, aplicando regras de negócio para organização contábil e evitando duplicidades.

---

## 🚀 Funcionalidades

* **Leitura Inteligente de PDFs:** Extrai o texto interno dos documentos para identificar automaticamente o tipo de documento, valor pago, data de vencimento/pagamento e o beneficiário.
* **Padronização de Nomenclatura:**
  * Comprovantes comuns: `COMPROVANTE [VALOR] [BENEFICIÁRIO].pdf` (em caixa alta, limitando o nome da empresa às duas primeiras palavras e removendo códigos numéricos iniciais).
  * Guias Fiscais: `COMPROVANTE [VALOR] DARF [DATA].pdf`.
* **Tratamento de Conflitos e Duplicidades:**
  * Compara o conteúdo dos arquivos para ignorar cópias idênticas.
  * Em caso de pagamentos distintos com mesmo valor e beneficiário, adiciona automaticamente o dia e mês (`DD-MM`) para evitar sobrescrita.

---

## 🛠️ Tecnologias Utilizadas

* **Python 3**
* **PyPDF:** Extração de texto estruturado de arquivos PDF.
* **Expressões Regulares (Regex):** Captura precisa de valores monetários, datas e razões sociais.
* **OS / Hashlib:** Manipulação segura de arquivos no sistema operacional e verificação de integridade.

---

## 📦 Como Executar

1. **Instale a dependência:**
   ```bash
   pip install pypdf
