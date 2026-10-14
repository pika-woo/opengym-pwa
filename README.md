# openGym PWA (personal static build)

Personal static build of [openGym](https://github.com/DuarteSantos8/openGym)
(`VITE_DEMO=1`, no backend) for use on iPhone via Safari → *Add to Home Screen*.

- Built from upstream `main` (v1.4.1) with one small patch: `VITE_DEMO_SEED=0`
  skips the example-data seed so the app starts empty (see `PATCH.md`).
- All data stays in the browser's localStorage on the device. Nothing is sent anywhere.
- Back up regularly: Settings → Data & backup → Export.

## Rebuild

```sh
git clone https://github.com/DuarteSantos8/openGym
# apply PATCH.md, then:
cd openGym/frontend && npm install
VITE_DEMO=1 VITE_DEMO_SEED=0 npm run build
# copy frontend/dist/* to this repo's branch root and push
```

## License

[GNU Affero General Public License v3.0](https://github.com/DuarteSantos8/openGym/blob/main/LICENSE)
— same as upstream openGym. Corresponding source: the upstream repository above,
plus the patch described in `PATCH.md`.
