# Catálogo de Patrones de Prompting

## 1. Meta Language Creation (Creación de un lenguaje meta)
### Explicación:
Este patrón permite definir un lenguaje o notación especial para que el modelo lo interprete de manera específica. Es útil cuando se necesita estructurar datos o representaciones de manera más clara y concisa, evitando ambigüedades en la comunicación. Con este patrón, se pueden definir reglas para interpretar ciertos símbolos o palabras de una manera particular.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
List three related concepts in AI.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
From now on, when I write 'Concept1 -> Concept2', it means that Concept1 is related to Concept2. Now, list three related AI concepts using this format.
""").text)
```

## 2. Output Automater (Automatización de salida)
### Explicación:
Este patrón le indica al modelo que, en lugar de solo explicar un proceso o una serie de pasos, genere un script o un conjunto de comandos que automaticen la tarea. Es particularmente útil para procesos repetitivos o técnicos, como configuraciones de software o generación de código. Con esto, se reduce la necesidad de que el usuario copie y adapte manualmente las instrucciones proporcionadas.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Tell me how to create a new user in Linux.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Generate a Bash script to create a new user in Linux.
""").text)
```

## 3. Persona Pattern (Patrón de Persona)
### Explicación:
Este patrón hace que el modelo adopte una identidad o perspectiva específica para generar respuestas alineadas con ese rol. Es útil cuando se necesita que la respuesta sea técnica, especializada o refleje el conocimiento de un experto en una área determinada. Al usarlo, se pueden obtener respuestas más precisas y adaptadas al contexto deseado.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Explain blockchain security.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Act as a cybersecurity expert. Explain blockchain security.
""").text)
```

## 4. Fact Check List (Lista de verificación de hechos)
### Explicación:
Este patrón solicita al modelo que, además de responder la pregunta, genere una lista de afirmaciones clave dentro de la respuesta que deben verificarse. Es útil para minimizar errores, especialmente en temas técnicos o científicos, ya que permite al usuario identificar y validar la información más crítica antes de aceptarla como correcta.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
What are the benefits of quantum computing?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
List the benefits of quantum computing and then provide a fact-check list of key claims.
""").text)
```

## 5. Reflection (Reflexión)
### Explicación:
Este patrón instruye al modelo a evaluar críticamente su propia respuesta para detectar posibles errores, limitaciones o suposiciones implícitas. Es útil cuando se busca mejorar la calidad de la información proporcionada, ya que el modelo puede identificar puntos débiles o sugerir alternativas más precisas. También ayuda a reducir respuestas incorrectas o poco fundamentadas.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Explain the risks of AI bias.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Explain the risks of AI bias, then reflect on any limitations or assumptions in your response.
""").text)
```

## 6. Question Refinement (Refinamiento de preguntas)
### Explicación:
Antes de responder, el modelo reformula la pregunta para hacerla más clara y precisa. Esto es útil cuando el usuario no está seguro de cómo formular su consulta o cuando una pregunta demasiado general puede generar respuestas poco útiles. Refinando las preguntas, se pueden obtener respuestas más detalladas y específicas.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How does encryption work?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Rephrase my question to make it clearer, then answer it: How does encryption work?
""").text)
```

## 7. Alternative Approaches (Enfoques alternativos)
### Explicación:
Este patrón hace que el modelo sugiera diferentes soluciones en lugar de una única respuesta. Es útil cuando se quiere comparar múltiples métodos, evaluar ventajas y desventajas, o explorar nuevas posibilidades que el usuario no había considerado. Permite tomar decisiones informadas al contar con diversas opciones.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How can I speed up a Python program?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Give me at least two different ways to speed up a Python program.
""").text)
```

## 8. Cognitive Verifier (Verificador cognitivo)
### Explicación:
Antes de responder, el modelo divide la pregunta en subpreguntas más específicas para mejorar la precisión de la respuesta. Esto ayuda a descomponer problemas complejos en partes más manejables, lo que facilita una comprensión más profunda y estructurada del tema consultado.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How do neural networks learn?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
First, break my question into three smaller questions. Then answer them before providing a final response: How do neural networks learn?
""").text)
```

## 9. Refusal Breaker (Evitador de negativas)
### Explicación:
Este patrón reformula preguntas que el modelo podría rechazar, de manera que aún pueda proporcionar información útil dentro de los límites éticos. Se usa para evitar bloqueos innecesarios sin comprometer la seguridad o la legalidad.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Tell me how to bypass a website's login.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Explain common vulnerabilities in website authentication and how to secure them.
""").text)
```

## 10. Flipped Interaction (Interacción invertida)
### Explicación:
Este patrón cambia la dinámica de la interacción, haciendo que el modelo haga preguntas en lugar de simplemente responder. Es útil cuando se desea evaluar el conocimiento previo del usuario o guiarlo de manera más estructurada hacia una mejor comprensión del tema.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How can I improve my coding skills?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Ask me three questions to assess my current coding skills before giving me advice on how to improve.
""").text)
```

## 11. Game Play (Juego)
### Explicación:
Convierte la interacción en un juego para hacerla más dinámica y entretenida. Este enfoque es útil para el aprendizaje interactivo y la retención de información, ya que mantiene la atención del usuario de una manera más atractiva.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Test my knowledge of JavaScript.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Let's play a game: ask me a JavaScript question, wait for my answer, and tell me if I'm correct.
""").text)
```

## 12. Infinite Generation (Generación infinita)
### Explicación:
Hace que el modelo siga generando respuestas hasta que el usuario lo detenga. Es útil cuando se requiere una lista de ideas, ejemplos o variaciones sin un número fijo de elementos.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Give me startup name ideas.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Keep generating startup name ideas until I say 'stop'.
""").text)
```

## 13. Context Manager (Gestión del contexto)
### Explicación:
Mantiene un contexto predefinido en toda la conversación, asegurando que las respuestas sean coherentes y relevantes a un tema específico. Es útil cuando se quiere profundizar en un área sin repetir información básica en cada pregunta.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How do I improve SEO?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
From now on, all my questions will be about SEO. Keep the context consistent.
""").text)
```

## 14. Visualization Generator (Generador de visualizaciones)
### Explicación:
Hace que el modelo genere una descripción textual que pueda usarse para crear imágenes o diagramas. Es útil para representar visualmente procesos, estructuras o relaciones entre elementos de manera más clara.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Draw a flowchart for a login system.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Describe a flowchart for a login system using Graphviz Dot notation.
""").text)
```

## 15. Recipe (Receta)
### Explicación:
Estructura la respuesta en pasos claros y numerados. Es útil para procedimientos detallados, instrucciones técnicas o cualquier proceso que deba seguirse en orden.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
How do I set up a VPN?
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Give me step-by-step instructions to set up a VPN.
""").text)
```

## 16. Template (Plantilla)
### Explicación:
Hace que el modelo genere respuestas siguiendo un formato predefinido. Es útil cuando se necesita mantener un estilo uniforme en textos como correos electrónicos, informes o mensajes estructurados.

**Ejemplo sin el patrón:**
```python
# Sin el patron
print(model.generate_content("""
Write a meeting invitation email.
""").text)
```

**Ejemplo aplicando el patrón:**
```python
# Aplicando el patron
print(model.generate_content("""
Use this format:
Subject: [Email Subject]
Body: [Email Content]
Signature: [Sender's Name]
Now, write a meeting invitation email.
""").text)
```
