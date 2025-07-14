
# dotenvx - Secure, Layered & Encrypted Environment Management

[![npm version](https://img.shields.io/npm/v/@dotenvx/dotenvx?color=red&style=social&logo=dotenvx)](https://www.npmjs.com/package/@dotenvx/dotenvx)
[![dotenvx](https://img.shields.io/badge/dotenvx-000000?logoColor=yellow&style=social&logo=dotenv)](https://www.npmjs.com/package/@dotenvx/dotenvx)

<br>

>> Modern `.env` management with encryption, environment layering, and convention-based loading. Secure secrets even in public repos.
> Advanced `.env` on steroids.

<br>
<hr>
<br>

##  Features

-  Encrypted `.env` file support (`.env.enc`)
-  Multi-environment layering (`.env`, `.env.local`, `.env.production`, etc.)
-  Seamless CLI + programmatic usage
-  Framework support (Node.js, Next.js, Vite, etc.)
-  Secure team collaboration with encrypted env sharing

<br>
<hr>
<br>

##  Installation

```bash
npm install @dotenvx/dotenvx
```

Global install (optional):

```bash
npm install -g @dotenvx/dotenvx
```

## Note 
Use `npx @dotenvx/dotenvx` if using the module without global install
Use `dotenvx` if using global install

<br>
<hr>
<br>

##  Usage

###  Run Scripts with Environment Variables

```bash
dotenvx run -- node index.js
```
```bash
npx @dotenvx/dotenvx run -- node index.js
```

With multiple `.env` files (last overrides first):

```bash
dotenvx run -f .env.local -f .env -- node app.js
```
```bash
npx @dotenvx/dotenvx run -f .env.local -f .env -- node app.js
```

###  Encrypt / Decrypt `.env` Files

#### Encrypt:

```bash
dotenvx encrypt -f .env
```
```bash
npx @dotenvx/dotenvx encrypt -f .env
```

This creates:

* `.env.enc` – Encrypted version (✅ safe to commit)
* `.env.keys` – Private key (❌ do not commit)

#### Decrypt:

```bash
dotenvx decrypt -f .env
```
```bash
@dotenvx/dotenvx decrypt -f .env
```

<br>
<hr>
<br>

##  Example Scripts (`package.json`)

```json
{
  "scripts": {
    "dev": "dotenvx run -- node index.js",
    "build": "dotenvx run -f .env.production -- node build.js",
    "encrypt": "dotenvx encrypt -f .env",
    "decrypt": "dotenvx decrypt -f .env",
    "rotate": "dotenvx rotate -f .env",
    "your command": "dotenvx run -- your command"
  }
}
```

<br>
<hr>
<br>

##  Programmatic Usage (Node.js)

```js
import dotenvx from '@dotenvx/dotenvx';

dotenvx.config({ path: '.env', overload: true,debug:true });
console.log('Loaded:', process.env.API_KEY);
```

```js
import '@dotenvx/dotenvx/config';
console.log('Loaded:', process.env.API_KEY);
```

<br>
<hr>
<br>

##  Use Cases

*  Secure secrets in public or open-source repositories
*  Use multiple environments in mono-repos
*  Dev/CI/CD workflows that need predictable env layering
*  Secret rotation and encryption at deployment

<br>
<hr>
<br>

##  Framework Support

*  Node.js / Express
*  Vite / React / Vue
*  Next.js (`--convention=nextjs`)
*  Works with Bun, Deno, Ruby, Go (via dotenvx.org ecosystem)

<br>
<hr>
<br>

##  .gitignore Recommendation

```gitignore
.env
.env.keys
```

```bash
npx @dotenvx/dotenvx ext gitignore --pattern .env.keys #to gitignore .env.keys
```
```bash
dotenvx ext gitignore --pattern .env.keys #to gitignore .env.keys
```

>  You can safely commit `.env.enc` to version control as it's encrypted.

<br>
<hr>
<br>

##  Security Tips

* Never commit `.env` or `.env.keys`
* Rotate sensitive variables regularly
* Store `.env.keys` securely (1Password, Vault, etc.)

<br>
<hr>
<br>

##  Learn More

*  [Official Docs](https://dotenvx.com/docs)
*  [Why dotenvx?](https://dotenvx.com/blog/2024/06/24/dotenvx-next-generation-config-management.html)
*  [Next.js Setup](https://dotenvx.com/docs/frameworks/nextjs)

<br>
<hr>
<br>


> PRs welcome! Star the repo 🌟 if you found it useful.

<br>
<hr>
<br>

##  License

MIT License:
<br>

[![View License](https://img.shields.io/badge/Licence-white?style=social&logo=github)](LICENSE)


