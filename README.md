# Del riesgo a la estrategia óptima

Experiencia web educativa de la cátedra Teoría de la Decisión de la Universidad Nacional de Río Negro.

**Actividad publicada:** [abrir la experiencia interactiva](https://tddunrn-gif.github.io/preferencias-riesgo-aplicacion/)

La página se publica automáticamente mediante GitHub Actions.

## Recorrido didáctico

La primera parte elicita una función de utilidad individual mediante tres fractiles adaptativos, con un máximo de cuatro comparaciones por fractil y dos pruebas predictivas. Cada lotería muestra su valor esperado.

La segunda parte aplica esa curva al caso ficticio **BioValle Envases**, una empresa del Alto Valle que evalúa tres escalas para producir bandejas compostables a partir de orujo de manzana. El alumno controla el avance y no necesita realizar cálculos. La experiencia incorpora, en orden:

1. formulación, matriz de pagos y árbol;
2. criterios de decisión sin probabilidades;
3. probabilidades previas y valor esperado;
4. estudio imperfecto, revisión bayesiana y estrategia contingente;
5. valor de la información muestral y perfecta;
6. utilidad esperada individual;
7. equivalentes ciertos y primas de riesgo;
8. valor personal de la información y comparación final de decisiones.

Los pagos del caso se expresan en millones de pesos constantes y permanecen dentro del intervalo de elicitación de −50 a 50.

## Privacidad y almacenamiento

La aplicación solicita un código de participante y advierte que no se deben ingresar nombres, DNI ni correos electrónicos. Firebase Authentication genera una identidad anónima. Las reglas de Firestore permiten escribir solamente el documento asociado con esa identidad y no habilitan lecturas desde la aplicación pública.

La configuración concreta del SDK web se conserva como el secreto `FIREBASE_CONFIG_JSON` de GitHub Actions. Durante la publicación se genera `firebase-config.runtime.js`, que no forma parte del árbol fuente. Como toda configuración de Firebase para la Web, sus valores siguen siendo observables en el navegador. La protección de los datos depende de la autenticación, las reglas de Firestore y las restricciones del proyecto.

Las respuestas integradas se guardan en la colección `integratedResponses`. El documento incorpora primero la encuesta y luego el estado y el resultado de la aplicación.

## Configuración

1. Habilitar el acceso anónimo en Firebase Authentication.
2. Crear Firestore y publicar `firestore.rules`.
3. Guardar el objeto JSON de configuración como el secreto `FIREBASE_CONFIG_JSON` del repositorio.
4. Configurar GitHub Pages para publicar mediante GitHub Actions.
5. Ejecutar el flujo incluido en `.github/workflows/deploy-pages.yml`.

La actividad funciona sin Firebase, pero en ese caso advierte que no pudo confirmar el guardado y permite descargar la experiencia completa como JSON.

## Licencias

- El código fuente se distribuye bajo la [Licencia MIT](LICENSE).
- Los textos, consignas y demás contenidos educativos se distribuyen bajo [Creative Commons Atribución 4.0 Internacional](LICENSE-CONTENT.md).
