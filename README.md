OmniGas es una plataforma de interoperabilidad y digitalización para el sector gasolinero. Actúa como puente (middleware) entre los sistemas de control de las estaciones y el consumidor final. Nuestra solución permite transformar cualquier gasolinera tradicional en una estación inteligente y autosustentable, donde el usuario puede localizar, pagar, despacharse y facturar automáticamente desde una única interfaz, reduciendo costos operativos para la empresa y eliminando la fricción administrativa para el cliente. Para el Frontend propongo utilizar Flutter(Dart) pues crea una interfaz única y fluida para iOS y Android. Gestiona la geolocalización, escaneo de QRs y la comunicación NFC para habilitar la bomba. Para el backend, Flask(python) pues recibe las peticiones de la App, se comunica con los sistemas de la gasolinera y coordina las validaciones de pago y facturación, esto en conjunto con Facturama o Finkok API para realizar el "Timbrado" fiscal ante el SAT de forma inmediata al confirmar el despacho de gasolina, generando el PDF sin intervención humana. Stripe API para el proceso de las transacciones y liberación del combustible. PostgreSQL para la DB mediante SQLAlchemy para la facilitación de la comunicación entre Flask y la DB permitiendo una gestión de datos escalable y limpia. Google Cloud para la escalabilidad y seguridad. FLUJO de la estación smart: 1. El usuairio selecciona el monto en la app, OmniGas genera el NFC para el usuario y envía una señal al sistema de control volumétrico de la gasolinera para liberar la bomba seleccionada(self-service) 2. Una vez terminado el despacho, el sistema de la bomba envía "carga terminada" al backend 3. Flask toma los datos de la carga y el perfil fiscal del usuario, los envía a la API del PAC y entrega la factura al correo del cliente.


OmniGas - Middleware de Interoperabilidad Gasolinera


Stack Tecnológico
- Frontend: Flutter (Dart) - Multiplataforma iOS/Android.
- Backend: Flask (Python) - Arquitectura de microservicios.
- Base de Datos: PostgreSQL con SQLAlchemy.
- Infraestructura: Google Cloud Platform.

Arquitectura de la Solución
El sistema actúa como un Middleware que orquesta la comunicación entre:
1. Pasarelas de pago (Stripe).
2. Sistemas de control volumétrico (Protocolos industriales).
3. Proveedores Autorizados de Certificación (PACs) para timbrado CFDI.

Estado del Proyecto
Actualmente en fase de Prototipado Técnico (TRL 3).
