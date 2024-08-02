# Repro of an issue installing sqlite within a shadow-cljs project

## Error

```bash
$ npx shadow-cljs compile app
shadow-cljs - config: ./shadow-cljs.edn
[:app] Compiling ...
Failed to inspect file
  ./node_modules/@sqlite.org/sqlite-wasm/sqlite-wasm/jswasm/sqlite3-bundler-friendly.mjs

Errors encountered while trying to parse file
  ./node_modules/@sqlite.org/sqlite-wasm/sqlite-wasm/jswasm/sqlite3-bundler-friendly.mjs
  {:line 13822, :column 10, :message "'}' expected"}
zsh: exit 1     npx shadow-cljs compile app

```

## `sqlite3-bundler-friendly.mjs`

The relevant portion of the mjs file in question

```js
class OpfsSAHPool {
          vfsDir;

L13822    #dhVfsRoot;

          #dhOpaque;

          #dhVfsParent;

          #mapSAHToName = new Map();

          #mapFilenameToSAH = new Map();

          #availableSAH = new Set();

          #mapS3FileToOFile_ = new Map();

          #apBody = new Uint8Array(HEADER_CORPUS_SIZE);

          #dvBody;

          #cVfs;

          #verbosity;

```
