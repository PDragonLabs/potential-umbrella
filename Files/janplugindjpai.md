 

**Create a Jan Plugin Using TypeScript**

**Template for Quick Start**

Utilize this repository as a foundation for building your TypeScript-based Jan plugin.

* Head to the Jan plugin template repository: ([https://github.com/janhq/extension-template](https://github.com/janhq/extension-template))
* Select "Use this template" to form a new repository.
* Choose a fitting owner and name for your repository.
* Click "Create repository."
* Clone the new repository onto your local system.

**Initial Setup**

Follow these steps to prepare your development environment after cloning.

* **Note:** You'll require a fairly up-to-date Node.js version. Consider 'nodenv' or 'nvm' for version management.  If using these, 'nodenv install' in the repository's root will set up the appropriate version. Otherwise, Node.js 20.x or newer should work.

* **Dependency Installation:** 
   ```bash
   npm install
   ```

* **TypeScript Build:**
   ```bash
   npm run bundle 
   ```

* **Artifact Verification:**
    You'll find a .tgz file within your plugin's directory.

**Metadata Updates**

Your plugin's information is contained within 'package.json'.  Modify these fields:

* **name:** A distinct name for your plugin.
* **description:**  Concisely outline your plugin's functionality.
* **version:**  Update as needed.

**The Heart of Your Plugin: Code**

Focus your development efforts within the 'src/' directory.  Let's cover some essentials:

* The majority of Jan plugin extension functions work asynchronously, returning a `Promise<any>`.
* Refer to Jan's documentation for in-depth information on the Jan Plugin Core module (`@janhq/core`).

**Illustrative Example (`index.ts`)**

```typescript
import { core } from "@janhq/core";

async function displayMessage(): Promise<any> {
  await core.showMessage("Hello from my Jan plugin!");
  return; 
}

// Register your plugin functions with Jan
core.registerPluginFunc("displayMessage", displayMessage);
```

**Testing and Packaging**

* Meticulously test your plugin inside Jan to guarantee its behavior.
* Use `npm run bundle`  to generate a distributable package.

**Important Notes**

* **UI Customization:** Jan plugins can alter user interface components. This might involve utilizing web technologies (HTML, CSS, JavaScript).

* **Documentation:**  Clear, well-written documentation aids plugin users during installation and use.
 
