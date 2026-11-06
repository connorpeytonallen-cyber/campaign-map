# Campaign Map — setup guide

The website is the **`charleston-map`** folder. Everything else here (this guide, `serve.ps1`) is just for you.

- Players open one link and see the map. They can zoom and click pins. They can't change anything.
- Only you can edit. You publish with a private GitHub key that's stored only in your browser.
- The map is locked to the area in your screenshot. There are no labels, airports or other places marked on it.

---

## 1. Put it online (free, one time, about 10 minutes)

1. Create a free GitHub account at <https://github.com/signup>.
2. Click **+** (top right) → **New repository**. Name it `campaign-map`, choose **Public**, then click **Create repository**.
3. On the new repository page, click **"uploading an existing file"**. Open the `charleston-map` folder on your computer, select **everything inside it** (`index.html`, `css`, `js`, `data`, `images`, `.nojekyll`) and drag it onto the page. Click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment* choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then click **Save**.
5. Wait 1–2 minutes. Your map is now at
   **`https://YOUR-USERNAME.github.io/campaign-map/`**
   That's the link to send your players.

## 2. Make your editing key (one time)

1. Go to <https://github.com/settings/personal-access-tokens/new>.
2. **Token name:** `Campaign map editor`. **Expiration:** pick a date (up to a year).
3. **Repository access:** *Only select repositories* → `campaign-map`.
4. **Permissions → Repository permissions → Contents → Read and write.**
5. Click **Generate token** and copy it.
6. Open **`https://YOUR-USERNAME.github.io/campaign-map/#edit`**, go to the **Settings** tab, then **Publishing**. Paste the key and press **Test connection**.

Keep the key private. If it ever leaks, delete it on the same GitHub page and make a new one.

## 3. Editing the map

1. Open your map with **`#edit`** at the end of the address.
2. **+ Add pin**, then click the map where it goes.
3. Fill in the pin's details:
   - **Name** and **Description.** Formatting: `**bold**`, `*italic*`, `[link text](https://…)`, and a line starting with `- ` makes a bullet.
   - **Title font**, **Text font** and **Text size.** There are 19 fonts, including fantasy ones like Cinzel, MedievalSharp, Uncial Antiqua and Pirata One.
   - **Pin color.**
   - **Image (optional).** Upload one from your computer (big photos are shrunk automatically) or paste an image link.
4. **Drag a pin** to move it, or click it in the list to edit it.
5. Press **Publish**. Players see the change within a minute or two.

Changes are saved on your device as you go, so nothing is lost if you close the tab before publishing.
**Exit editor** shows you exactly what players see.
**Settings** also has the map's name (you can show it on the map), default fonts and color for pins, and **Download data file** (a backup).

The two pins already on the map are examples. Delete them whenever you like.

## Who can change it?

Only someone holding your key. If a player types `#edit`, they get a practice copy in their own browser that can't be published.

## Good to know

- Map data © OpenStreetMap contributors; map tiles by CARTO. CARTO's tiles are free for personal, non-commercial use. Leave the small credit in the corner.
- To see the site on your own computer before uploading, run this in the folder that contains `serve.ps1`, then open <http://localhost:8080/>:
  `powershell -ExecutionPolicy Bypass -File serve.ps1`
