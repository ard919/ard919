npm init -y
npm install express body-parser
import express from 'express';
import bodyParser from 'body-parser';

const app = express();
app.use(bodyParser.json());

// Configurar la ruta raíz para responder a preguntas
app.get('/', (req, res) => {
  res.send('Bienvenido al asistente personal IA!');
});

// Configurar una ruta para manejar preguntas
app.post('/ask', (req, res) => {
  const pregunta = req.body.pregunta;
  // Aquí iría el código para procesar la pregunta y generar una respuesta
  const respuesta = 'Lo siento, no entendí tu pregunta';
  res.send(respuesta);
});

// Iniciar el servidor
const port = process.env.PORT || 3000;
app.listen(port, () => {
  console.log(`Servidor escuchando en el puerto ${port}`);
});
