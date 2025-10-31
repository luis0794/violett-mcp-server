# Violett MCP Server

Servidor MCP (Model Context Protocol) completo basado en el ejemplo de `simpleStreamableHttp.ts` del [typescript-sdk oficial](https://github.com/modelcontextprotocol/typescript-sdk).

## Características

Este servidor MCP incluye:

### 🔧 Herramientas (Tools)
- **fetch_url**: Realiza peticiones HTTP GET para obtener contenido de URLs
- **post_data**: Envía datos mediante peticiones HTTP POST

### 💡 Prompts
- **summarize_url**: Genera un resumen del contenido de una URL
- **analyze_api**: Analiza la estructura de respuesta de una API

### 📊 Recursos (Resources)
- **stream://example**: Recurso de ejemplo con streaming de datos
- **http(s)://...**: Soporte para recursos HTTP dinámicos

## Quick Start

¿Quieres empezar rápidamente? Sigue estos pasos:

### 1. Instalación y configuración
```bash
# Clona el repositorio
git clone https://github.com/luis0794/violett-mcp-server.git
cd violett-mcp-server

# Instala las dependencias
npm install
```

### 2. Ejecuta el servidor
```bash
# Modo desarrollo (recomendado para pruebas)
npm run dev

# O en modo producción
npm run build && npm start
```

### 3. Prueba las herramientas
Una vez que el servidor esté ejecutándose, puedes probar las herramientas disponibles:

- **Obtener contenido de una URL**:
  ```bash
  # Usa la herramienta fetch_url
  # Ejemplo: obtener contenido de https://httpbin.org/json
  ```

- **Enviar datos a una API**:
  ```bash
  # Usa la herramienta post_data
  # Ejemplo: enviar datos a https://httpbin.org/post
  ```

### 4. Integración con cliente MCP
Copia la configuración del archivo `mcp-config.json` a tu cliente MCP favorito para empezar a usar las herramientas inmediatamente.

## Instalación

```bash
npm install
```

## Compilación

```bash
npm run build
```

## Uso

### Modo desarrollo (TypeScript directo)
```bash
npm run dev
# o específicamente para MCP:
npm run mcp
```

### Modo producción (JavaScript compilado)
```bash
npm start
```

## Integración con Clientes MCP

Para usar este servidor desde un cliente MCP, puedes usar la configuración incluida en `mcp-config.json`:

```json
{
  "mcpServers": {
    "violett-mcp-server": {
      "command": "npx",
      "args": ["-y", "ts-node", "src/examples/single-node-server.ts"],
      "cwd": ".",
      "env": {}
    }
  }
}
```

## Ejemplo de uso

Una vez conectado, el servidor proporciona herramientas para:

1. **Obtener contenido web**:
   - Usar la herramienta `fetch_url` con parámetro `url`
   
2. **Enviar datos a APIs**:
   - Usar la herramienta `post_data` con parámetros `url` y `data`

3. **Generar prompts inteligentes**:
   - `summarize_url`: Para resumir contenido de una URL
   - `analyze_api`: Para analizar respuestas de API

## Estructura del proyecto

```
violett-mcp-server/
├── src/
│   └── examples/
│       └── single-node-server.ts    # Servidor MCP principal
├── dist/                            # JavaScript compilado
├── mcp-config.json                  # Configuración para clientes MCP
├── package.json
└── README.md
```

## Desarrollo basado en el SDK oficial

Este servidor está basado en el ejemplo `simpleStreamableHttp.ts` del [Model Context Protocol TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk/blob/main/src/examples/server/simpleStreamableHttp.ts).

Para más información sobre MCP, consulta la [documentación oficial](https://github.com/modelcontextprotocol/typescript-sdk?tab=readme-ov-file#quick-start).