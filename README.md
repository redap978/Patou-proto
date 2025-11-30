<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PATOU</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #56ab2f 0%, #a8e063 100%);
            min-height: 100vh;
            padding: 10px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            margin-bottom: 20px;
            text-align: center;
        }

        h1 {
            color: #56ab2f;
            font-size: 2em;
            margin-bottom: 5px;
        }

        .logo {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        nav {
            display: flex;
            gap: 8px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 15px;
        }

        .tab-btn {
            background: linear-gradient(135deg, #56ab2f 0%, #a8e063 100%);
            color: white;
            border: none;
            padding: 10px 18px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 14px;
            transition: all 0.2s;
        }

        .tab-btn.active {
            background: linear-gradient(135deg, #2d6b1a 0%, #56ab2f 100%);
            transform: scale(1.05);
        }

        .content {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            display: none;
        }

        .content.active {
            display: block;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            color: #333;
            font-weight: 600;
        }

        input, select {
            width: 100%;
            padding: 10px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 16px;
        }

        input:focus, select:focus {
            outline: none;
            border-color: #56ab2f;
        }

        .submit-btn {
            background: linear-gradient(135deg, #56ab2f 0%, #a8e063 100%);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
            margin-top: 10px;
        }

        .animal-card {
            background: linear-gradient(135deg, #56ab2f 0%, #a8e063 100%);
            color: white;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 15px;
            position: relative;
        }

        .delete-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255,255,255,0.3);
            border: none;
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        .conseil-btn {
            background: white;
            color: #56ab2f;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            margin-top: 10px;
            font-weight: bold;
            width: 100%;
        }

        .shop-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .product-card {
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
        }

        .product-icon {
            font-size: 3em;
            margin-bottom: 10px;
        }

        .price {
            color: #56ab2f;
            font-size: 1.3em;
            font-weight: bold;
            margin: 10px 0;
        }

        .buy-btn {
            background: #56ab2f;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 15px;
            cursor: pointer;
            width: 100%;
        }

        .vet-card {
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
        }

        .vet-card h4 {
            color: #56ab2f;
            margin-bottom: 5px;
        }

        .rating {
            color: #ffc107;
            font-size: 1.2em;
            margin-top: 10px;
        }

        .advice-section {
            background: #f0f9e8;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .advice-section h3 {
            color: #56ab2f;
            margin-bottom: 15px;
        }

        .advice-item {
            background: white;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 10px;
            border-left: 4px solid #56ab2f;
        }

        .hero {
            text-align: center;
            padding: 20px 0;
        }

        .hero h2 {
            color: #56ab2f;
            font-size: 1.5em;
            margin-bottom: 10px;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .feature-card {
            text-align: center;
            padding: 15px;
            border-radius: 10px;
            background: #f0f9e8;
        }

        .feature-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .alert {
            background: #4caf50;
            color: white;
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 15px;
            display: none;
            text-align: center;
        }

        .alert.show {
            display: block;
        }

        .empty-state {
            text-align: center;
            color: #666;
            padding: 30px;
        }

        .map-container {
            width: 100%;
            height: 250px;
            background: #f0f0f0;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">🐾</div>
            <h1>Patou</h1>
            <p>Bien-être animal</p>
            <nav>
                <button class="tab-btn active" onclick="showTab('accueil')">🏠</button>
                <button class="tab-btn" onclick="showTab('profil')">➕</button>
                <button class="tab-btn" onclick="showTab('mesanimaux')">📋</button>
                <button class="tab-btn" onclick="showTab('conseils')">💡</button>
                <button class="tab-btn" onclick="showTab('shop')">🛒</button>
                <button class="tab-btn" onclick="showTab('veto')">📍</button>
            </nav>
        </header>

        <div id="accueil" class="content active">
            <div class="hero">
                <h2>Bienvenue sur Patou !</h2>
                <p>Tout pour le bien-être de votre animal</p>
            </div>
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">🐕</div>
                    <h3>Profils</h3>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💡</div>
                    <h3>Conseils</h3>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🛒</div>
                    <h3>Boutique</h3>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📍</div>
                    <h3>Vétérinaires</h3>
                </div>
            </div>
        </div>

        <div id="profil" class="content">
            <h2>➕ Ajouter un animal</h2>
            <div id="alert" class="alert"></div>
            <form id="animalForm">
                <div class="form-group">
                    <label>Nom</label>
                    <input type="text" id="nom" placeholder="Ex: Rex" required>
                </div>
                <div class="form-group">
                    <label>Espèce</label>
                    <select id="espece" required>
                        <option value="">Choisir...</option>
                        <option value="chien">🐕 Chien</option>
                        <option value="chat">🐈 Chat</option>
                        <option value="oiseau">🦜 Oiseau</option>
                        <option value="lapin">🐰 Lapin</option>
                        <option value="rongeur">🐹 Rongeur</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Race</label>
                    <select id="race" required>
                        <option value="">Sélectionnez d'abord une espèce</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Taille (cm)</label>
                    <input type="number" id="taille" placeholder="Ex: 50" min="1" required>
                </div>
                <div class="form-group">
                    <label>Poids (kg)</label>
                    <input type="number" id="poids" placeholder="Ex: 15" min="0.1" step="0.1" required>
                </div>
                <button type="submit" class="submit-btn">💾 Enregistrer</button>
            </form>
        </div>

        <div id="mesanimaux" class="content">
            <h2>📋 Mes animaux</h2>
            <div id="animauxListe">
                <p class="empty-state">Aucun animal enregistré 🐾</p>
            </div>
        </div>

        <div id="conseils" class="content">
            <h2>💡 Conseils</h2>
            <div id="conseilsContent">
                <p class="empty-state">Enregistrez un animal pour voir les conseils !</p>
            </div>
        </div>

        <div id="shop" class="content">
            <h2>🛒 Boutique</h2>
            <div class="shop-grid">
                <div class="product-card">
                    <div class="product-icon">🦴</div>
                    <h3>Croquettes</h3>
                    <div class="price">29,99 €</div>
                    <button class="buy-btn" onclick="acheter('Croquettes')">Acheter</button>
                </div>
                <div class="product-card">
                    <div class="product-icon">🐟</div>
                    <h3>Pâtée</h3>
                    <div class="price">19,99 €</div>
                    <button class="buy-btn" onclick="acheter('Pâtée')">Acheter</button>
                </div>
                <div class="product-card">
                    <div class="product-icon">🎾</div>
                    <h3>Jouets</h3>
                    <div class="price">14,99 €</div>
                    <button class="buy-btn" onclick="acheter('Jouets')">Acheter</button>
                </div>
                <div class="product-card">
                    <div class="product-icon">🛏️</div>
                    <h3>Panier</h3>
                    <div class="price">39,99 €</div>
                    <button class="buy-btn" onclick="acheter('Panier')">Acheter</button>
                </div>
            </div>
        </div>

        <div id="veto" class="content">
            <h2>📍 Vétérinaires</h2>
            <div id="map" style="width:100%;height:400px;border-radius:10px;margin-bottom:20px;"></div>
            <div class="vet-card">
                <h4>🏥 Clinique Centre</h4>
                <p>Paris - 01 23 45 67 89</p>
                <div class="rating">⭐⭐⭐⭐⭐</div>
                <p style="color:#666;">127 avis</p>
            </div>
            <div class="vet-card">
                <h4>🏥 Cabinet Dr. Martin</h4>
                <p>Lyon - 04 12 34 56 78</p>
                <div class="rating">⭐⭐⭐⭐☆</div>
                <p style="color:#666;">89 avis</p>
            </div>
        </div>
    </div>

    <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB41DRUbKWJHPxaFjMAwdrzWzbVKartNGg&callback=initMap" async defer></script>
    <script>
        let map;
        let markers = [];

        function initMap() {
            // Centre sur Paris
            map = new google.maps.Map(document.getElementById('map'), {
                center: { lat: 48.8566, lng: 2.3522 },
                zoom: 6
            });

            // Vétérinaires avec leurs coordonnées
            const vetos = [
                { nom: '🏥 Clinique Centre', ville: 'Paris', tel: '01 23 45 67 89', lat: 48.8566, lng: 2.3522, note: '⭐⭐⭐⭐⭐', avis: 127 },
                { nom: '🏥 Cabinet Dr. Martin', ville: 'Lyon', tel: '04 12 34 56 78', lat: 45.7640, lng: 4.8357, note: '⭐⭐⭐⭐☆', avis: 89 },
                { nom: '🏥 Clinique Animalia', ville: 'Marseille', tel: '04 98 76 54 32', lat: 43.2965, lng: 5.3698, note: '⭐⭐⭐⭐⭐', avis: 203 },
                { nom: '🏥 Veto Plus', ville: 'Toulouse', tel: '05 61 22 33 44', lat: 43.6047, lng: 1.4442, note: '⭐⭐⭐⭐☆', avis: 156 },
                { nom: '🏥 Clinique des Animaux', ville: 'Nice', tel: '04 93 55 66 77', lat: 43.7102, lng: 7.2620, note: '⭐⭐⭐⭐⭐', avis: 98 },
                { nom: '🏥 Cabinet Vétérinaire', ville: 'Nantes', tel: '02 40 11 22 33', lat: 47.2184, lng: -1.5536, note: '⭐⭐⭐⭐☆', avis: 72 }
            ];

            // Ajouter les marqueurs
            vetos.forEach(veto => {
                const marker = new google.maps.Marker({
                    position: { lat: veto.lat, lng: veto.lng },
                    map: map,
                    title: veto.nom,
                    icon: {
                        url: 'data:image/svg+xml;charset=UTF-8,' + encodeURIComponent(`
                            <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 40 40">
                                <circle cx="20" cy="20" r="18" fill="#56ab2f" stroke="white" stroke-width="3"/>
                                <text x="20" y="27" font-size="20" text-anchor="middle" fill="white">🏥</text>
                            </svg>
                        `)
                    }
                });

                // Info bulle au clic
                const infoWindow = new google.maps.InfoWindow({
                    content: `
                        <div style="padding:10px;min-width:200px;">
                            <h3 style="color:#56ab2f;margin:0 0 10px 0;">${veto.nom}</h3>
                            <p style="margin:5px 0;"><strong>Ville:</strong> ${veto.ville}</p>
                            <p style="margin:5px 0;"><strong>Tel:</strong> ${veto.tel}</p>
                            <p style="margin:5px 0;font-size:1.2em;">${veto.note}</p>
                            <p style="margin:5px 0;color:#666;">${veto.avis} avis</p>
                        </div>
                    `
                });

                marker.addListener('click', () => {
                    // Fermer toutes les autres infos
                    markers.forEach(m => m.infoWindow.close());
                    infoWindow.open(map, marker);
                });

                markers.push({ marker, infoWindow });
            });
        }

        const races = {
            chien: ['Labrador', 'Golden Retriever', 'Berger Allemand', 'Bulldog', 'Beagle'],
            chat: ['Persan', 'Maine Coon', 'Siamois', 'British Shorthair', 'Bengal'],
            oiseau: ['Perruche', 'Canari', 'Perroquet'],
            lapin: ['Nain', 'Bélier', 'Angora'],
            rongeur: ['Hamster', 'Cochon d\'Inde', 'Gerbille']
        };

        let animauxListe = [];
        const icons = { chien: '🐕', chat: '🐈', oiseau: '🦜', lapin: '🐰', rongeur: '🐹' };

        document.getElementById('espece').addEventListener('change', function() {
            const raceSelect = document.getElementById('race');
            raceSelect.innerHTML = '<option value="">Choisir une race</option>';
            
            if (this.value && races[this.value]) {
                races[this.value].forEach(race => {
                    const opt = document.createElement('option');
                    opt.value = race;
                    opt.textContent = race;
                    raceSelect.appendChild(opt);
                });
            }
        });

        function showTab(tab) {
            document.querySelectorAll('.content').forEach(c => c.classList.remove('active'));
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            document.getElementById(tab).classList.add('active');
            event.target.classList.add('active');
            
            if (tab === 'mesanimaux') afficherAnimaux();
        }

        document.getElementById('animalForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            animauxListe.push({
                id: Date.now(),
                nom: document.getElementById('nom').value,
                espece: document.getElementById('espece').value,
                race: document.getElementById('race').value,
                taille: document.getElementById('taille').value,
                poids: document.getElementById('poids').value
            });

            showAlert('✅ Animal enregistré !');
            this.reset();
            
            // Afficher automatiquement dans l'onglet "Mes Animaux"
            afficherAnimaux();
            showTab('mesanimaux');
            document.querySelectorAll('.tab-btn')[2].classList.add('active');
        });

        function afficherAnimaux() {
            const container = document.getElementById('animauxListe');
            
            if (animauxListe.length === 0) {
                container.innerHTML = '<p class="empty-state">Aucun animal enregistré 🐾</p>';
                return;
            }
            
            container.innerHTML = animauxListe.map(a => `
                <div class="animal-card">
                    <button class="delete-btn" onclick="supprimerAnimal(${a.id})">🗑️</button>
                    <h3>${icons[a.espece]} ${a.nom}</h3>
                    <p><strong>Espèce:</strong> ${a.espece}</p>
                    <p><strong>Race:</strong> ${a.race}</p>
                    <p><strong>Taille:</strong> ${a.taille} cm</p>
                    <p><strong>Poids:</strong> ${a.poids} kg</p>
                    <button class="conseil-btn" onclick="voirConseils('${a.espece}','${a.nom}','${a.race}')">💡 Conseils</button>
                </div>
            `).join('');
        }

        function supprimerAnimal(id) {
            if (confirm('Supprimer cet animal ?')) {
                animauxListe = animauxListe.filter(a => a.id !== id);
                afficherAnimaux();
                showAlert('✅ Animal supprimé');
            }
        }

        function voirConseils(espece, nom, race) {
            const conseils = {
                chien: [
                    { titre: '🚶 Exercice', texte: '30-60 min d\'exercice par jour' },
                    { titre: '🍖 Alimentation', texte: '2 repas par jour adaptés' },
                    { titre: '💉 Vaccins', texte: 'Rappels annuels obligatoires' }
                ],
                chat: [
                    { titre: '🎯 Jeux', texte: '15-30 min de jeu quotidien' },
                    { titre: '🍽️ Nourriture', texte: 'Libre service préférable' },
                    { titre: '🧹 Litière', texte: 'Nettoyage quotidien' }
                ],
                oiseau: [
                    { titre: '🏠 Cage', texte: 'Espace suffisant pour voler' },
                    { titre: '🌾 Alimentation', texte: 'Graines, fruits, légumes' },
                    { titre: '🎵 Social', texte: 'Interaction quotidienne' }
                ],
                lapin: [
                    { titre: '🥬 Foin', texte: '80% de l\'alimentation' },
                    { titre: '🏃 Liberté', texte: '3-4h hors cage par jour' },
                    { titre: '🦷 Dents', texte: 'Usure naturelle par le foin' }
                ],
                rongeur: [
                    { titre: '🏠 Espace', texte: 'Cage avec plusieurs niveaux' },
                    { titre: '🌙 Rythme', texte: 'Actif la nuit' },
                    { titre: '🥜 Nourriture', texte: 'Graines et légumes' }
                ]
            };

            const c = conseils[espece] || [];
            document.getElementById('conseilsContent').innerHTML = `
                <div class="advice-section">
                    <h3>Conseils pour ${nom} (${race})</h3>
                    ${c.map(i => `
                        <div class="advice-item">
                            <h4>${i.titre}</h4>
                            <p>${i.texte}</p>
                        </div>
                    `).join('')}
                </div>
            `;
            
            showTab('conseils');
            document.querySelectorAll('.tab-btn')[3].classList.add('active');
        }

        function acheter(produit) {
            showAlert('🛒 ' + produit + ' ajouté au panier !');
        }

        function showAlert(msg) {
            const alert = document.getElementById('alert');
            alert.textContent = msg;
            alert.classList.add('show');
            setTimeout(() => alert.classList.remove('show'), 3000);
        }
    </script>
</body>
</html>
