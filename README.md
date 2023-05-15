# Intalación de Jest en angular 
Instalación y configuración de Jest en angular

1. Remover cualquier referencia de  Jasmine y Karma en package.json.

```
npm remove <karma karma-chrome-launcher Jasmin...>
```

2. Instalar Jest como dependencia de desarrollo

```
npm install --save-dev jest jest-preset-angular @types/jest
```

3. Crear el archivo con el nombre ```setup-jest.ts``` en la carpeta raiz del proyecto y realizar la importacion del siguiente paquete.

```
import 'jest-preset-angular/setup-jest';
```

4. Agregar en el packege.json, la configuracion de jest

```package.json
"jest": {
    "preset": "jest-preset-angular",
    "setupFilesAfterEnv": [
      "<rootDir>/setup-jest.ts"
    ],
    "globalSetup": "jest-preset-angular/global-setup",
      "collectCoverage": true,
        "collectCoverageFrom": [
          "./src/**"
        ],
        "coverageThreshold": {
          "global": {
            "lines": 90
          }
        }
  }
```
5. Configurar JEST en tsconfig.json y tsconfig.spec.json
```tsconfig.json
"types": [
  "jest"
],
 "esModuleInterop": true
```
5. Configurar JEST en tsconfig.spec.json
```tsconfig.json
"types": [
  "jest"
]
```

7.Configurar los comandos para ejecutar las pruebas en el package.json
```package.json
"test": "jest",
"test:watch": "jest --watchAll",
```
8. (Opcional) Remover karma.config.js y el archivo test.ts

