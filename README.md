# Intégration du logo fourni par l'utilisateur directement dans le fichier HTML
# en l'encodant en base64 pour que le site soit autonome (sans fichier séparé).

import base64

# Lire le logo et le convertir en base64
logo_path = "/mnt/data/04867342-7872-45D9-9AB6-188C2704B8F2.png"
with open(logo_path, "rb") as img_file:
    logo_base64 = base64.b64encode(img_file.read()).decode("utf-8")

# Créer la nouvelle version HTML avec logo intégré
html_with_logo = f"""
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shop Numeric - Boostez votre carrière</title>
    <style>
        body {{ font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f9f9f9; color: #333; }}
        header {{ background: #0a1a2f; color: white; padding: 20px; text-align: center; }}
        header img {{ max-height: 80px; }}
        nav {{ margin-top: 10px; }}
        nav a {{ color: white; margin: 0 15px; text-decoration: none; font-weight: bold; }}
        .hero {{ text-align: center; padding: 60px 20px; background: linear-gradient(to right, #0a1a2f, #0f3460); color: white; }}
        .hero h1 {{ font-size: 2.5em; margin-bottom: 15px; }}
        .hero p {{ font-size: 1.2em; }}
        .btn {{ display: inline-block; margin-top: 20px; padding: 12px 25px; background: #1e90ff; color: white; text-decoration: none; border-radius: 5px; font-weight: bold; }}
        .services {{ padding: 50px 20px; text-align: center; }}
        .services h2 {{ margin-bottom: 30px; }}
        .service-item {{ background: white; padding: 20px; margin: 10px; display: inline-block; width: 250px; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); vertical-align: top; }}
        footer {{ background: #0a1a2f; color: white; text-align: center; padding: 20px; margin-top: 30px; }}
        footer a {{ color: #1e90ff; text-decoration: none; }}
    </style>
</head>
<body>
    <header>
        <img src="data:image/png;base64,{logo_base64}" alt="Logo Shop Numeric">
        <nav>
            <a href="#">Accueil</a>
            <a href="#services">Nos Services</a>
            <a href="#ebook">Ebook</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section class="hero">
        <h1>Boostez votre carrière avec Shop Numeric 🚀</h1>
        <p>Ebooks, CV & Lettres, Coaching emploi</p>
        <a href="https://wa.me/224629312267" class="btn">Contactez-nous sur WhatsApp</a>
    </section>

    <section class="services" id="services">
        <h2>Nos Services</h2>
        <div class="service-item">
            <h3>Ebooks pratiques</h3>
            <p>Téléchargez nos guides pour réussir vos candidatures.</p>
        </div>
        <div class="service-item">
            <h3>Création de CV & Lettres</h3>
            <p>Des documents professionnels qui font la différence.</p>
        </div>
        <div class="service-item">
            <h3>Coaching emploi</h3>
            <p>Préparez vos entretiens avec un accompagnement personnalisé.</p>
        </div>
    </section>

    <footer id="contact">
        <p>📩 Email : <a href="mailto:shopnumeric.gn@gmail.com">shopnumeric.gn@gmail.com</a></p>
        <p>📱 WhatsApp : <a href="https://wa.me/224629312267">+224 629 312 267</a></p>
        <p>🌐 Facebook : Shop Numeric</p>
        <p>&copy; 2025 Shop Numeric - Tous droits réservés</p>
    </footer>
</body>
</html>
"""

# Sauvegarde du fichier HTML final
final_file_path = "/mnt/data/shop_numeric_final.html"
with open(final_file_path, "w", encoding="utf-8") as f:
    f.write(html_with_logo)

final_file_path
