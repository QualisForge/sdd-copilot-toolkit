# Gate README: ¿puede otra persona usar la solución?

- ¿README explica qué hace la aplicación y qué funciones están terminadas?
- ¿Requisitos previos y su instalación están verificados y no incluyen secretos?
- ¿Indica **exactamente** cómo iniciar: abrir archivo de entrada o ejecutar comando desde la carpeta correcta?
- ¿Explica **qué se ve**: nombre de página/pantalla, archivo de destino o URL local verificada y qué comprobar al abrir?
- ¿Distingue Mac y Windows solo cuando las acciones/comandos cambian?
- ¿Explica cómo usar la solución, detener servidor si existe y ejecutar tests automatizados con resultado esperado?
- ¿Los comandos han sido probados realmente? Si no: marcar «Pendiente de validar» y no afirmar que funcionan.
- ¿En nueva historia se conservaron y actualizaron las instrucciones anteriores?
- ¿README se revisó en VALIDATE y se incluyó en CLOSE?

**Aplicación HTML estática:** si fue verificado que abre mediante doble clic en `index.html`, ese es un paso válido para ambos sistemas; si necesita servidor, documentar comando y URL que efectivamente funcionaron. No inventar puertos.
