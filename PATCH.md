# Patch applied on top of upstream openGym main (v1.4.1)

Build flags: `VITE_DEMO=1 VITE_DEMO_SEED=0`

`VITE_DEMO_SEED` is a new build-time flag (default `1` = upstream behaviour):

- `frontend/src/lib/demo.js`: added
  `export const DEMO_SEED = import.meta.env.VITE_DEMO_SEED !== '0'`
- `frontend/src/store/useStore.js`: the demo seed (`resetDemo()`) now only runs
  when `DEMO_SEED` is true; the app otherwise starts with an empty guest profile.
- `frontend/src/views/Login.jsx`: with `DEMO_SEED=0` the welcome screen says
  "Your gym log" / "Start training" instead of "Live demo" / "Start the demo".
- `frontend/src/views/Settings.jsx`: with `DEMO_SEED=0` the Demo section is
  titled "Your data", the info row no longer mentions example data, the
  "Reset demo data" row is hidden (it would re-seed example data), and the
  guest-mode note is shown.
- `frontend/src/locales/ko.js`: Korean translations for the new strings.

Nothing else was changed. To reproduce: apply the above to a fresh upstream
checkout and build with `VITE_DEMO=1 VITE_DEMO_SEED=0 npm run build`.
