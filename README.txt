1) Instale o framework pipenv
$ pip install pipenv

2)Instale o flask no ambiente virtual pipenv
$ pipenv install Flask

3) Teste o código subindo o flask no ambiente pipenv
$ pipenv run flask --app index run

4) Instale componentes da Vercel
$ npm install i -g vercel

5) Rode o vercel (Caso tenha problema com política, abra o powershell com premissão de administrador e rode Set-ExecutionPolicy RemoteSigned)
$ vercel 

6) Configure (utilizei essa configuração)

Vercel CLI 28.8.0
? Set up and deploy “C:\FeAmorim\Estudos_e_Projetos\Python\EstudoPython\Python\Piloto_Deploy_Vercel”? [Y/n] y
? Which scope do you want to deploy to? nandoalpha
? Link to existing project? [y/N] n
? What’s your project’s name? piloto-deploy-vercel
? In which directory is your code located? ./
? Want to modify these settings? [y/N] n

7) Após os passos, gerou essas infromações:
🔗  Linked to nandoalpha/piloto-deploy-vercel (created .vercel and added it to .gitignore)
🔍  Inspect: https://vercel.com/nandoalpha/piloto-deploy-vercel/7MxJxLkbeZBC2af8wWVxwE2DXfTq [1s]
✅  Production: https://piloto-deploy-vercel.vercel.app [8s]
📝  Deployed to production. Run `vercel --prod` to overwrite later (https://vercel.link/2F).
💡  To change the domain or build command, go to https://vercel.com/nandoalpha/piloto-deploy-vercel/settings

8) Crie o arquivo vercel.json (https://andrewbaisden.medium.com/how-to-deploy-a-python-flask-app-to-vercel-ff4a63d312f4)
{
    "version": 2,
    "builds": [
        {
            "src": "./index.py",
            "use": "@vercel/python"
        }
    ],
    "routes": [
        {
            "src": "/(.*)",
            "dest": "/"
        }
    ]
}

9) Crie o arquivo requirements.txt (para a vercel saber o requisito mínimo)
$ pip freeze > requirements.txt

10) Envie para deploy  vercel
$ vercel --prod

11) Confira se subiu
https://piloto-deploy-vercel.vercel.app