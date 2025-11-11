# peru-express
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perú Express - Descubre el Perú y el Mundo</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Header y Navegación */
        header {
            background: linear-gradient(135deg, #c1272d 0%, #ffffff 50%, #c1272d 100%);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #c1272d;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #333;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
            padding: 0.5rem 1rem;
            border-radius: 5px;
        }

        .nav-links a:hover {
            color: #c1272d;
            background: rgba(193, 39, 45, 0.1);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), 
                        url('https://images.unsplash.com/photo-1587595431973-160d0d94add1?w=1600') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            margin-top: 70px;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInDown 1s;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s;
        }

        .cta-button {
            background: #c1272d;
            color: white;
            padding: 1rem 2.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(193, 39, 45, 0.5);
        }

        /* Secciones */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            color: #c1272d;
            margin-bottom: 3rem;
            position: relative;
            padding-bottom: 1rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: #c1272d;
        }

        /* Grid de Destinos */
        .destinations-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .destination-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .destination-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        .destination-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .destination-info {
            padding: 1.5rem;
        }

        .destination-info h3 {
            color: #c1272d;
            margin-bottom: 0.5rem;
            font-size: 1.5rem;
        }

        .destination-info p {
            color: #666;
        }

        /* Historia Section */
        .history-timeline {
            background: linear-gradient(135deg, #fff 0%, #f8f8f8 100%);
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .timeline-item {
            display: flex;
            margin-bottom: 2rem;
            padding-bottom: 2rem;
            border-bottom: 2px solid #c1272d;
        }

        .timeline-date {
            font-size: 2rem;
            font-weight: bold;
            color: #c1272d;
            min-width: 200px;
        }

        .timeline-content {
            padding-left: 2rem;
        }

        .timeline-content h3 {
            color: #333;
            margin-bottom: 0.5rem;
        }

        /* Gastronomía */
        .gastronomy-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .dish-card {
            text-align: center;
            padding: 2rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .dish-card:hover {
            transform: scale(1.05);
        }

        .dish-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .dish-card h3 {
            color: #c1272d;
            margin-bottom: 0.5rem;
        }

        /* Plan de Viaje */
        .trip-planner {
            background: linear-gradient(135deg, #c1272d 0%, #e63946 100%);
            color: white;
            padding: 3rem;
            border-radius: 15px;
            text-align: center;
        }

        .trip-form {
            max-width: 600px;
            margin: 2rem auto;
            display: grid;
            gap: 1rem;
        }

        .trip-form input, .trip-form select, .trip-form textarea {
            padding: 1rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
        }

        .trip-form button {
            background: white;
            color: #c1272d;
            padding: 1rem;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .trip-form button:hover {
            transform: scale(1.05);
        }

        /* Mapa */
        .map-container {
            width: 100%;
            height: 500px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        /* Destinos Internacionales */
        .international-destinations {
            background: #f8f8f8;
            padding: 3rem;
            border-radius: 15px;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #c1272d 0%, #8b1a1f 100%);
            color: white;
            padding: 3rem 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: transform 0.3s;
            text-decoration: none;
        }

        .social-links a:hover {
            transform: scale(1.2);
        }

        /* Animaciones */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                flex-direction: column;
                gap: 0.5rem;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }

            .timeline-item {
                flex-direction: column;
            }

            .timeline-date {
                margin-bottom: 1rem;
            }

            .timeline-content {
                padding-left: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">🇵🇪 PERÚ EXPRESS</div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#destinos">Destinos</a></li>
                <li><a href="#historia">Historia</a></li>
                <li><a href="#gastronomia">Gastronomía</a></li>
                <li><a href="#planifica">Planifica</a></li>
                <li><a href="#mapa">Mapa</a></li>
                <li><a href="#internacional">Internacional</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="hero-content">
            <h1>Descubre el Perú</h1>
            <p>Un país de historia milenaria, paisajes increíbles y sabores únicos</p>
            <a href="#destinos" class="cta-button">Explorar Destinos</a>
        </div>
    </section>

    <!-- Destinos del Perú -->
    <section id="destinos">
        <h2 class="section-title">Lugares que Debes Visitar en Perú</h2>
        <div class="destinations-grid">
            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1587595431973-160d0d94add1?w=600" alt="Machu Picchu" class="destination-image">
                <div class="destination-info">
                    <h3>🏔️ Machu Picchu</h3>
                    <p>La joya de la arquitectura inca, una de las Siete Maravillas del Mundo Moderno. Ubicada en Cusco, esta ciudadela del siglo XV te transportará en el tiempo.</p>
                </div>
            </div>
            
            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1531968455001-5c5272a41129?w=600" alt="Cusco" class="destination-image">
                <div class="destination-info">
                    <h3>⛪ Cusco</h3>
                    <p>La antigua capital del Imperio Inca, una ciudad que mezcla arquitectura colonial con restos incaicos. Su Plaza de Armas es impresionante.</p>
                </div>
            </div>

            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1596461246752-396351d31a8f?w=600" alt="Lima" class="destination-image">
                <div class="destination-info">
                    <h3>🏛️ Lima</h3>
                    <p>La capital gastronómica de América, con su centro histórico declarado Patrimonio de la Humanidad y su impresionante malecón frente al Pacífico.</p>
                </div>
            </div>

            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1608662211909-5d5eff6c16f0?w=600" alt="Lago Titicaca" class="destination-image">
                <div class="destination-info">
                    <h3>🌊 Lago Titicaca</h3>
                    <p>El lago navegable más alto del mundo, hogar de las fascinantes islas flotantes de los Uros y la Isla Taquile.</p>
                </div>
            </div>

            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1526392060635-9d6019884377?w=600" alt="Arequipa" class="destination-image">
                <div class="destination-info">
                    <h3>🌋 Arequipa</h3>
                    <p>La Ciudad Blanca, rodeada de volcanes y conocida por su arquitectura colonial de sillar blanco. Puerta de entrada al Cañón del Colca.</p>
                </div>
            </div>

            <div class="destination-card">
                <img src="https://images.unsplash.com/photo-1621894864385-f771e6f0e2e3?w=600" alt="Amazonia" class="destination-image">
                <div class="destination-info">
                    <h3>🌴 Amazonía Peruana</h3>
                    <p>La selva más biodiversa del planeta. Iquitos y Puerto Maldonado son puertas a aventuras inolvidables en la jungla.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Historia del Perú -->
    <section id="historia">
        <h2 class="section-title">Historia del Perú</h2>
        <div class="history-timeline">
            <div class="timeline-item">
                <div class="timeline-date">3000 a.C.</div>
                <div class="timeline-content">
                    <h3>Civilizaciones Preincaicas</h3>
                    <p>Surgen las primeras civilizaciones como Caral, considerada la ciudad más antigua de América. Le siguen culturas como Chavín, Nazca, Moche, Chimú y más.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-date">1438</div>
                <div class="timeline-content">
                    <h3>Imperio Inca</h3>
                    <p>El Tahuantinsuyo se convierte en el imperio más grande de América precolombina, abarcando desde Colombia hasta Chile, con Cusco como su capital.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-date">1532</div>
                <div class="timeline-content">
                    <h3>Conquista Española</h3>
                    <p>Francisco Pizarro llega a Perú y captura al emperador Atahualpa en Cajamarca, marcando el inicio de la era colonial española.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-date">1821</div>
                <div class="timeline-content">
                    <h3>Independencia</h3>
                    <p>José de San Martín proclama la independencia del Perú el 28 de julio. Simón Bolívar consolida la libertad en la Batalla de Ayacucho (1824).</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-date">Siglo XX-XXI</div>
                <div class="timeline-content">
                    <h3>Perú Moderno</h3>
                    <p>El país se moderniza, enfrenta desafíos políticos y económicos, pero emerge como una potencia gastronómica y turística mundial.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gastronomía -->
    <section id="gastronomia">
        <h2 class="section-title">Gastronomía Peruana</h2>
        <p style="text-align: center; margin-bottom: 3rem; font-size: 1.2rem;">
            Reconocida como una de las mejores del mundo, fusionando sabores ancestrales con influencias de todo el planeta.
        </p>
        <div class="gastronomy-grid">
            <div class="dish-card">
                <div class="dish-icon">🍲</div>
                <h3>Ceviche</h3>
                <p>El plato bandera del Perú. Pescado fresco marinado en limón, con cebolla, ají y cilantro. Declarado Patrimonio Cultural de la Nación.</p>
            </div>

            <div class="dish-card">
                <div class="dish-icon">🍛</div>
                <h3>Lomo Saltado</h3>
                <p>Fusión chino-peruana: carne salteada con cebolla, tomate, ají amarillo, acompañado de arroz y papas fritas.</p>
            </div>

            <div class="dish-card">
                <div class="dish-icon">🐔</div>
                <h3>Ají de Gallina</h3>
                <p>Cremoso plato de pollo deshilachado en salsa de ají amarillo, leche y pan, servido con papas y arroz.</p>
            </div>

            <div class="dish-card">
                <div class="dish-icon">🥔</div>
                <h3>Causa Limeña</h3>
                <p>Puré de papa amarilla sazonado con limón y ají, relleno de pollo, atún o mariscos. Un arte culinario.</p>
            </div>

            <div class="dish-card">
                <div class="dish-icon">🦐</div>
                <h3>Anticuchos</h3>
                <p>Brochetas de corazón de res marinadas en ají panca y especias, asadas a la parrilla. Tradición desde la época colonial.</p>
            </div>

            <div class="dish-card">
                <div class="dish-icon">🍰</div>
                <h3>Suspiro Limeño</h3>
                <p>Postre tradicional a base de manjar blanco, cubierto con merengue de oporto. Dulce y delicado como un suspiro.</p>
            </div>
        </div>
    </section>

    <!-- Planifica tu Viaje -->
    <section id="planifica">
        <div class="trip-planner">
            <h2 style="font-size: 2.5rem; margin-bottom: 1rem;">✈️ Planifica tu Viaje a Perú</h2>
            <p style="font-size: 1.2rem; margin-bottom: 2rem;">Déjanos ayudarte a crear la aventura perfecta</p>
            
            <form class="trip-form" onsubmit="event.preventDefault(); alert('¡Gracias! Nos pondremos en contacto contigo pronto.');">
                <input type="text" placeholder="Nombre completo" required>
                <input type="email" placeholder="Correo electrónico" required>
                <input type="tel" placeholder="Teléfono / WhatsApp" required>
                
                <select required>
                    <option value="">¿Cuándo quieres viajar?</option>
                    <option>Este mes</option>
                    <option>Próximos 3 meses</option>
                    <option>3-6 meses</option>
                    <option>6-12 meses</option>
                    <option>Más de un año</option>
                </select>

                <select required>
                    <option value="">Duración del viaje</option>
                    <option>3-5 días</option>
                    <option>1 semana</option>
                    <option>2 semanas</option>
                    <option>3 semanas o más</option>
                </select>

                <select required>
                    <option value="">¿Qué te interesa más?</option>
                    <option>Cultura e Historia</option>
                    <option>Aventura y Naturaleza</option>
                    <option>Gastronomía</option>
                    <option>Todo incluido</option>
                </select>

                <textarea placeholder="Cuéntanos más sobre tu viaje ideal..." rows="4"></textarea>
                
                <button type="submit">Solicitar Plan Personalizado</button>
            </form>

            <div style="margin-top: 3rem;">
                <h3 style="font-size: 1.5rem; margin-bottom: 1rem;">📋 Consejos para tu Viaje:</h3>
                <ul style="text-align: left; max-width: 600px; margin: 0 auto; line-height: 2;">
                    <
