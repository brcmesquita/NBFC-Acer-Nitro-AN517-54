# NBFC Configuration for Acer Nitro AN517-54  

📢 **Procurando colaboradores!** Precisamos de ajuda para aperfeiçoar o controle da ventoinha neste modelo de notebook.  

## ❓ Por que este repositório?  
O **Acer Nitro AN517-54** não possui suporte oficial no **NBFC (Notebook Fan Control)**, e muitos usuários enfrentam problemas de superaquecimento porque as ventoinhas não ajustam corretamente no Linux.  

Este repositório é um esforço para criar uma configuração funcional do NBFC para esse modelo, contando com a colaboração da comunidade.  

## 🔍 Testes realizados  
Foram testadas configurações baseadas nos seguintes modelos:  

| Modelo Testado       | Funcionou? | Observações |
|----------------------|------------|-------------|
| **AN515-51**        | ❌ Não      | Não aceita comandos corretamente |
| **AN515-57**        | ⚠️ Parcial  | Comportamento inconsistente |
| **AN515-58**        | ⚠️ Parcial  | Comportamento inconsistente |
| **Acer G3 Predator**| ❌ Não      | Não percebi se funcionou |
| **AN715-51**        | ⚠️ Parcial  | **Funcionou inicialmente**, aceitando comandos de velocidade manual, mas parou após reiniciar. Não testei se a velocidade aumentaria com o aquecimento da CPU ou GPU |

📌 **Conclusão até agora:** A configuração baseada no **AN715-51** foi a única que apresentou algum sucesso, mas ainda precisa ser ajustada para funcionar de forma estável.  

## 🚀 Como instalar e testar  

### 1️⃣ Instale o NBFC para Linux no Arch Linux  
```sh
yay -S nbfc-linux
```
Ou manualmente:  
```sh
git clone https://github.com/nbfc-linux/nbfc-linux.git
cd nbfc-linux
make && sudo make install
```

### 2️⃣ Copie o arquivo de configuração  
```sh
sudo cp "configs/Acer Nitro AN517-54.json" /usr/share/nbfc/configs/
```

### 3️⃣ Selecione e inicie o NBFC  
```sh
sudo nbfc config -s "Acer Nitro AN517-54"
sudo systemctl enable --now nbfc.service
```

### 4️⃣ Ajuste manualmente a velocidade das ventoinhas  
```sh
sudo nbfc set -s 100   # Define a velocidade para 100%
sudo nbfc status       # Verifica o status atual
```

## 🔧 Como você pode ajudar  
Se você tem um **Acer Nitro AN517-54**, sua ajuda pode ser essencial!  

✅ **Teste diferentes configurações**, especialmente a baseada no **AN715-51**.  
✅ **Edite `Acer Nitro AN517-54.json`** e tente ajustar o comportamento das ventoinhas.  
✅ **Relate suas experiências** e logs na aba de Issues.  

## 📬 Contribua com o projeto  
💬 **Tem uma configuração melhor?** Envie um **Pull Request**.  
🐞 **Encontrou problemas?** Abra um **Issue** e compartilhe detalhes.  
🛠️ **Quer testar novas configurações?** Faça um fork e experimente!  

🔥 **Vamos resolver esse problema juntos e manter nossos Nitro mais frios!**  
