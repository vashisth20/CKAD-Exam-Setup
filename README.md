# 🧠 CKAD Exam Prep – Quick Setup & Tips

Before starting the CKAD exam, spend the **first 2–3 minutes** preparing your environment. This will **save you time** on every single question.

---

## ✅ Step 1: Configure `.bashrc`

Open the terminal and run:

```bash
vi ~/.bashrc
```

Paste the following shortcuts:

```bash
alias k='kubectl'
alias kn='kubectl config set-context --current --namespace'
alias kc='kubectl config get-contexts'
alias kg='kubectl get'
alias ka='kubectl apply -f'
alias ke='kubectl explain --recursive'

export dr='--dry-run=client -o yaml'
export now='--grace-period=0 --force'
```

Save and apply changes:

```bash
source ~/.bashrc
```

## ✅ Step 2: Configure .vimrc (for YAML editing)

```bash
vi ~/.vimrc
```

Paste:

```vim
autocmd FileType yaml setlocal et ts=2 ai sw=2 sts=2
```

This improves indentation when editing YAML files in Vim (auto indent, 2 spaces, etc.).

## ✅ Step 3: Track Questions (Q1 to Q19)

To keep track of your progress during the exam:

```bash
echo -e "Q"{1..19}"= %\n"
```

Copy the output into the Mousepad/Notepad:

```makefile
Q1= %
Q2= %
Q3= %
...
Q19= %
```

As you go through the exam, update statuses like:

```ini
Q3= 8% Ingress question – svc left
Q5= 4% Partial – Netpol
```

This will help you prioritize what to revisit in the last 15–20 minutes.

## 💡 Aliases Explained

| Alias / Export | What It Does                                         |
| -------------- | ---------------------------------------------------- |
| `k`            | Short for `kubectl`                                  |
| `kn`           | Set current namespace (e.g., `kn default`)           |
| `kc`           | View current context                                 |
| `kg`           | Short for `kubectl get`                              |
| `ka`           | Apply a YAML file                                    |
| `ke`           | Explain fields recursively (e.g., `ke pod`)          |
| `dr`           | Use with `--dry-run=client -o yaml` to generate YAML |
| `now`          | Force delete a resource immediately                  |

### 🧪 Example Usage

```bash
k run nginx --image=nginx $dr > pod.yaml
vi pod.yaml
ka pod.yaml
```

## 📌 Notes

- This is 100% allowed in the CKAD exam.

- You can open one extra browser tab to view:

    - https://kubernetes.io

    - https://github.com (yes, your own public repo like this!)

- Do not use Google, StackOverflow, ChatGPT, or other tabs.
