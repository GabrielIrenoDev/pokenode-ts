# Changelog

## [4.0.0](https://github.com/GabrielIrenoDev/pokenode-ts/compare/v3.0.0...v4.0.0) (2026-09-28)


### ⚠ BREAKING CHANGES

* **models:** sync evolution and sprite models with PokéAPI ([#1412](https://github.com/GabrielIrenoDev/pokenode-ts/issues/1412))
* ItemClient#listItemFilingEffects is renamed to listItemFlingEffects. The old name was a typo — the endpoint is item-fling-effect, after the move Fling — and no alias is kept, because 2.0 already asks callers to revisit their imports. Behavior is unchanged.
* axios and axios-cache-interceptor are no longer peer dependencies. cacheOptions is replaced by cache?: CacheStore | false, and logs?: boolean by logger?: Logger. ClientArgs is renamed ClientOptions. Failed requests reject with PokenodeError instead of AxiosError; match it with isPokenodeError rather than instanceof, which is false across a duplicated ESM/CJS copy of the class. MainClient no longer extends BaseClient. getResourceByURL throws a TypeError on a URL that names no endpoint under the base URL, where it previously issued a malformed request. ENDPOINTS.POKEMON_LOCATION_AREA is removed; it held a template, not an endpoint.

### Features

* add base getListURL method ([d60cd73](https://github.com/GabrielIrenoDev/pokenode-ts/commit/d60cd73db287af3ed07f1be788f08155fbb1cb53))
* add chart, evolution helpers, and improve reporting utilities ([66fe213](https://github.com/GabrielIrenoDev/pokenode-ts/commit/66fe213c37a3dd339698158661bb30f81d4f4f81))
* add currency client ([fcaf732](https://github.com/GabrielIrenoDev/pokenode-ts/commit/fcaf7320b3af06241b5aa409845d9005b625aa4c))
* add lint staged ([4d9b772](https://github.com/GabrielIrenoDev/pokenode-ts/commit/4d9b77202c06237533c30b3d61d71d9167d56fb9))
* add rome setup ([b0af506](https://github.com/GabrielIrenoDev/pokenode-ts/commit/b0af50660582985c18d02e0d9111eeb7645341a3))
* Add Showdown animated sprites ([7f58c87](https://github.com/GabrielIrenoDev/pokenode-ts/commit/7f58c87313262258ee602f3a52325248ec9d3b7c))
* **build:** add banner to compiled files ([a8b75f3](https://github.com/GabrielIrenoDev/pokenode-ts/commit/a8b75f331c36ace2e558eb64f898f53c758d8b70))
* **cache:** add WebStorageCache ([e1f6690](https://github.com/GabrielIrenoDev/pokenode-ts/commit/e1f6690efd60d884ba6ae7c68c7eb01948152cf3))
* **client:** cancellation, pagination, resolution, retry and revalidation ([#1401](https://github.com/GabrielIrenoDev/pokenode-ts/issues/1401)) ([f9e8043](https://github.com/GabrielIrenoDev/pokenode-ts/commit/f9e8043dbdfea56bfac83df8753a7d62b26ebe67))
* **clients:** add getResourceByURL for a custom base URL [#903](https://github.com/GabrielIrenoDev/pokenode-ts/issues/903) ([85c5264](https://github.com/GabrielIrenoDev/pokenode-ts/commit/85c5264e9e315316b35ae825fd9d69b7fde957d3))
* **clients:** refactor clients ([1aeda60](https://github.com/GabrielIrenoDev/pokenode-ts/commit/1aeda60591cfeccb01e090f3dc5eebb435e5fdd3))
* **deps:** update axios ([23ffb36](https://github.com/GabrielIrenoDev/pokenode-ts/commit/23ffb36211892dd0bace190b44f2a472db0c7a35))
* **deps:** update axios ([a2daaff](https://github.com/GabrielIrenoDev/pokenode-ts/commit/a2daaff5d594ab143b4cc16cb42b77a314e51102))
* **deps:** update axios ([6854d7a](https://github.com/GabrielIrenoDev/pokenode-ts/commit/6854d7a72e08dff1b140a6f72132c9ed967ac5dd))
* **deps:** update axios-cache-interceptor ([43f6317](https://github.com/GabrielIrenoDev/pokenode-ts/commit/43f6317cd171797923c8517c83920b4d4ee17d0f))
* **deps:** update pino ([7fb05cd](https://github.com/GabrielIrenoDev/pokenode-ts/commit/7fb05cd237aeaf5b6a911d85c5fece3ca12313b2))
* **deps:** update pino ([5419a79](https://github.com/GabrielIrenoDev/pokenode-ts/commit/5419a79984fc25c7681c936e3194c01d1a3915a7))
* **deps:** update pino and pino-pretty ([3138c63](https://github.com/GabrielIrenoDev/pokenode-ts/commit/3138c6376d24af5b97293bebfe957eebe2f8bf24))
* **deps:** update pino version ([9c529e8](https://github.com/GabrielIrenoDev/pokenode-ts/commit/9c529e8b8c5137ce6ad5d22fc19fed10c0d4dd88))
* **docs:** add vitest ([9eda019](https://github.com/GabrielIrenoDev/pokenode-ts/commit/9eda0190d69dfc33418aa382b51acdd76f6979b4))
* **logger:** accept any debug/error logger ([5d3f30c](https://github.com/GabrielIrenoDev/pokenode-ts/commit/5d3f30c298fc87a5e0555ba975c4492cc8d6ad5d))
* **models:** change from interface to type ([e18d308](https://github.com/GabrielIrenoDev/pokenode-ts/commit/e18d30856639da3c1e3f9ba57225b8e95f00298c))
* **models:** infer what a resource link points at ([18fc63a](https://github.com/GabrielIrenoDev/pokenode-ts/commit/18fc63ae042da2af28eb4dc16751654cd40bfdf2))
* **models:** update pokemon typings ([7c0b066](https://github.com/GabrielIrenoDev/pokenode-ts/commit/7c0b066f8cf84278d3746b36a3840979f1cc5dfe))
* **models:** update pokemon typings and improve live tests ([0ca6a54](https://github.com/GabrielIrenoDev/pokenode-ts/commit/0ca6a54c3d2233cc5f56905836da655223545fa6))
* new axios cache, new build system and test runner ([73db8bc](https://github.com/GabrielIrenoDev/pokenode-ts/commit/73db8bce2da2fbb201644d934afd5f896e2f47b0))
* new build and release system ([7a0917a](https://github.com/GabrielIrenoDev/pokenode-ts/commit/7a0917a445dc311726fc168898f05bb91b6c8ada))
* refactor berry client ([70cdaa7](https://github.com/GabrielIrenoDev/pokenode-ts/commit/70cdaa786edfcd2161dd97823939aeda6bf803b0))
* replace axios with native fetch ([e331c65](https://github.com/GabrielIrenoDev/pokenode-ts/commit/e331c653515e0078ecfa5538e5126aa1a4878ff8))
* replace axios with native fetch ([6a34875](https://github.com/GabrielIrenoDev/pokenode-ts/commit/6a348756891ef764bd2570163e174a40886d3c19))
* **sprites:** add getPokemonSpriteUrl ([1a27766](https://github.com/GabrielIrenoDev/pokenode-ts/commit/1a277663305edef57c1863c36fc5573f1a143523))
* **tests:** add more tests ([81d8855](https://github.com/GabrielIrenoDev/pokenode-ts/commit/81d8855e8a596266cbddf03d0610cf78b6cde335))
* update axios and banner ([6de1aee](https://github.com/GabrielIrenoDev/pokenode-ts/commit/6de1aeebb559ccc3a6bfa493ccf76f558dfd601c))
* update evolution and pokemon typings ([3c17c1b](https://github.com/GabrielIrenoDev/pokenode-ts/commit/3c17c1b2a9d2994a5154afa29d1eeff5abb3e9c1))
* update to pnpm ([02e78d3](https://github.com/GabrielIrenoDev/pokenode-ts/commit/02e78d309e709b7e3c0601699fa6b0f87ba2b88e))


### Bug Fixes

* add coverage packages ([be03200](https://github.com/GabrielIrenoDev/pokenode-ts/commit/be03200a565a18fcf6c36550b7469242739224e2))
* add missing banner file ([57f85cf](https://github.com/GabrielIrenoDev/pokenode-ts/commit/57f85cf70a075a1094072c7e013b06f6d47d60e5))
* add past relations to Pokemon/Type ([b63ce9c](https://github.com/GabrielIrenoDev/pokenode-ts/commit/b63ce9c6cf90cef6a99d113efa39ed64ca64eaf9))
* add sonar properties ([067f1f6](https://github.com/GabrielIrenoDev/pokenode-ts/commit/067f1f6092e9bc2a91f217afd1abc5616b69727c))
* add swc core ([e0a9ed9](https://github.com/GabrielIrenoDev/pokenode-ts/commit/e0a9ed9953bb051c3deb93bac94003dd794536d1))
* api lists and logger ([58d341c](https://github.com/GabrielIrenoDev/pokenode-ts/commit/58d341cba052bfefca241938ee93eb69a55b524e))
* **base:** change base url enum to as const ([836cf91](https://github.com/GabrielIrenoDev/pokenode-ts/commit/836cf9198702d452831d7ec335f8be463754f033))
* **base:** fix get resource ([142f618](https://github.com/GabrielIrenoDev/pokenode-ts/commit/142f6186b4decc1f89df5bd2764c3983a99f773b))
* **base:** fix main client cache interceptor ([0d783c2](https://github.com/GabrielIrenoDev/pokenode-ts/commit/0d783c218ffddacc300525998a225690942ce473))
* **build:** minify in ci env ([eea3741](https://github.com/GabrielIrenoDev/pokenode-ts/commit/eea3741450698d1c3cd40ce208877b6f28d41ed1))
* **build:** tsdown config ([46f51c4](https://github.com/GabrielIrenoDev/pokenode-ts/commit/46f51c4c28c3f7c88491f78e44691ccd1e1aa638))
* change regex for utility function ([bfebbdc](https://github.com/GabrielIrenoDev/pokenode-ts/commit/bfebbdc40e85dec72b104c6ffddc6805407ac591))
* ci lint and format check ([b077e1a](https://github.com/GabrielIrenoDev/pokenode-ts/commit/b077e1ab4723309884160dcee5e62d4a94d1e975))
* **ci:** remove tsc lint from ci ([143728b](https://github.com/GabrielIrenoDev/pokenode-ts/commit/143728b9a17bea7814e639748c17626f417a4a0b))
* **ci:** update stable workflow ([35257bc](https://github.com/GabrielIrenoDev/pokenode-ts/commit/35257bc73718c7a30f6398214843bee649a8cfc7))
* **client:** report a response to every caller ([daf1ebf](https://github.com/GabrielIrenoDev/pokenode-ts/commit/daf1ebfebfbdd7393af3c72f022da9c49e3aeaf5))
* **clients:** change api access ([f926217](https://github.com/GabrielIrenoDev/pokenode-ts/commit/f926217c02b6325e055ab4ae2226e662b493416e))
* **clients:** remove unused axios typings ([a7794d8](https://github.com/GabrielIrenoDev/pokenode-ts/commit/a7794d82be4f71519152de06ecef70b17994737c))
* **clients:** remove useless constructors ([b6c057f](https://github.com/GabrielIrenoDev/pokenode-ts/commit/b6c057f7f638f2f7577010b2f7796c880687d508))
* **clients:** revert usage of URLSearchParams [#839](https://github.com/GabrielIrenoDev/pokenode-ts/issues/839) ([0d3b3f8](https://github.com/GabrielIrenoDev/pokenode-ts/commit/0d3b3f8bace93780894d7e3e911b1244f9eb83a1))
* comment sonar failed cove ([7565e1b](https://github.com/GabrielIrenoDev/pokenode-ts/commit/7565e1bf287c7ed8fff946fee26f6e05470e954f))
* **constants:** add protect move ailment ([#1407](https://github.com/GabrielIrenoDev/pokenode-ts/issues/1407)) ([1a556c8](https://github.com/GabrielIrenoDev/pokenode-ts/commit/1a556c8d5546569b47222b286436b5951ba90a34))
* **constants:** remove enums for readonly consts ([d57cb9c](https://github.com/GabrielIrenoDev/pokenode-ts/commit/d57cb9c9fbbc89c21d314b0a1be4915af78db297))
* **deps:** replace peers ad deps ([62eab27](https://github.com/GabrielIrenoDev/pokenode-ts/commit/62eab2722533d9a2337ffd3969854868fe80e7bd))
* **deps:** sync lockfile ([9cef17b](https://github.com/GabrielIrenoDev/pokenode-ts/commit/9cef17bc73d93974791b8e74ef8e2804a741ac06))
* **deps:** sync lockfiles ([5cb4a94](https://github.com/GabrielIrenoDev/pokenode-ts/commit/5cb4a9411060b48d2d27ac2960182955e7a49495))
* hide credential logging ([6ac8fa8](https://github.com/GabrielIrenoDev/pokenode-ts/commit/6ac8fa8151b20f7d856ceab68a05d803ad2b6096))
* **lint:** replace rome for biome ([3d71eba](https://github.com/GabrielIrenoDev/pokenode-ts/commit/3d71ebae1368ae9e1854b4c107903cc6b49cacbe))
* merge conflicts ([14777fc](https://github.com/GabrielIrenoDev/pokenode-ts/commit/14777fc784e57c7d46e30abf31326f015f99597a))
* **models:** add version to FlavorText interface ([a70e68a](https://github.com/GabrielIrenoDev/pokenode-ts/commit/a70e68a634bb035f1e39591d2c290b2d82db0c02))
* **models:** sync evolution and sprite models with PokéAPI ([#1412](https://github.com/GabrielIrenoDev/pokenode-ts/issues/1412)) ([3e5b0f0](https://github.com/GabrielIrenoDev/pokenode-ts/commit/3e5b0f04887a7a7e7e545ce354e3b0eaea8cbd91))
* pin nodejs version ([20ce8b0](https://github.com/GabrielIrenoDev/pokenode-ts/commit/20ce8b016c012c241095115a39b2d09ece36bcdd))
* pnpm lockfile ([8318627](https://github.com/GabrielIrenoDev/pokenode-ts/commit/8318627a95e9e3e88200c79ad11fd22d79540e23))
* remove pino and fix docs ([ebba1ae](https://github.com/GabrielIrenoDev/pokenode-ts/commit/ebba1ae1d596dee3f88b78f9a3a6de27f4c73dbb))
* remove unused files and modules ([3cb4f0d](https://github.com/GabrielIrenoDev/pokenode-ts/commit/3cb4f0d8863dcc2c21219b48641f60232e4743c8))
* remove unused jest config file ([c2a26eb](https://github.com/GabrielIrenoDev/pokenode-ts/commit/c2a26ebaa085f314f211f80cef8939f41881a4ef))
* sonarlint code smells [#827](https://github.com/GabrielIrenoDev/pokenode-ts/issues/827) ([2099d4c](https://github.com/GabrielIrenoDev/pokenode-ts/commit/2099d4c5601c759c99d3f9874157b2da05e9b5ec))
* sonarlint code smells [#827](https://github.com/GabrielIrenoDev/pokenode-ts/issues/827) ([ec83c7e](https://github.com/GabrielIrenoDev/pokenode-ts/commit/ec83c7e7dc45b16ef6282fcefff33f0cc92edc39))
* sync lockfile ([f42bfd1](https://github.com/GabrielIrenoDev/pokenode-ts/commit/f42bfd15710437f818fdd1cbef194e9183c3111e))
* **test:** replace test with describe ([0300095](https://github.com/GabrielIrenoDev/pokenode-ts/commit/0300095ce60596a4a69a22ce0ab1f48814f6b02a))
* typo ([d323b40](https://github.com/GabrielIrenoDev/pokenode-ts/commit/d323b40aab5ecb92aa9e0148b9657989feef7b71))
* typo ([ba71cc9](https://github.com/GabrielIrenoDev/pokenode-ts/commit/ba71cc9c00ad2b34e98e02f911d37a6ee2186516))
* update berry client ([9c81301](https://github.com/GabrielIrenoDev/pokenode-ts/commit/9c81301cf535e5946c5712bdd527f421c4e061e3))
* update sonar properties ([6776787](https://github.com/GabrielIrenoDev/pokenode-ts/commit/67767871d4e6c79cef92c0f157f71807fc9c6d62))


### Documentation

* overhaul documentation and .github ([38faee2](https://github.com/GabrielIrenoDev/pokenode-ts/commit/38faee2dbe24f64f0a839998f5f4da06b7aaa30e))

## [3.0.0](https://github.com/Gabb-c/pokenode-ts/compare/v2.3.1...v3.0.0) (2026-09-27)


### ⚠ BREAKING CHANGES

* **models:** sync evolution and sprite models with PokéAPI ([#1412](https://github.com/Gabb-c/pokenode-ts/issues/1412))

### Bug Fixes

* **models:** sync evolution and sprite models with PokéAPI ([#1412](https://github.com/Gabb-c/pokenode-ts/issues/1412)) ([40545d2](https://github.com/Gabb-c/pokenode-ts/commit/40545d20dca061992ea48fda3cc37d0cbcad8d7f))

## [2.3.1](https://github.com/Gabb-c/pokenode-ts/compare/v2.3.0...v2.3.1) (2026-09-04)


### Bug Fixes

* **constants:** add protect move ailment ([#1407](https://github.com/Gabb-c/pokenode-ts/issues/1407)) ([ffa0845](https://github.com/Gabb-c/pokenode-ts/commit/ffa0845e44670eb62792fe3ac922610b914534e5))

## [2.3.0](https://github.com/Gabb-c/pokenode-ts/compare/v2.2.0...v2.3.0) (2026-08-29)


### Features

* add chart, evolution helpers, and improve reporting utilities ([c72b218](https://github.com/Gabb-c/pokenode-ts/commit/c72b2181ab9c3de75aeeba7c8ee48c0f5613736e))

## [2.2.0](https://github.com/Gabb-c/pokenode-ts/compare/v2.1.0...v2.2.0) (2026-08-21)


### Features

* **client:** cancellation, pagination, resolution, retry and revalidation ([#1401](https://github.com/Gabb-c/pokenode-ts/issues/1401)) ([2d4c27d](https://github.com/Gabb-c/pokenode-ts/commit/2d4c27df022dd82e966388d75f0aa18b9dd8a18d))

## [2.1.0](https://github.com/Gabb-c/pokenode-ts/compare/v2.0.0...v2.1.0) (2026-08-17)


### Features

* **cache:** add WebStorageCache ([4b50329](https://github.com/Gabb-c/pokenode-ts/commit/4b50329db1caf1642450f8659b48dc307c8d904a))
* **logger:** accept any debug/error logger ([3d0b155](https://github.com/Gabb-c/pokenode-ts/commit/3d0b155785c3eecf7d134303d2210f08e6eca322))
* **models:** infer what a resource link points at ([1a35bda](https://github.com/Gabb-c/pokenode-ts/commit/1a35bda9ae080aa344418dec4cf1b94fc385df34))
* **models:** update pokemon typings and improve live tests ([fe71b07](https://github.com/Gabb-c/pokenode-ts/commit/fe71b076cb577dacf6188ef0cb6bbfa2a5959ef0))
* **sprites:** add getPokemonSpriteUrl ([dc617cd](https://github.com/Gabb-c/pokenode-ts/commit/dc617cd2cdabcbd55dd585c92c0b8babdfde6393))


### Bug Fixes

* api lists and logger ([8ee4a95](https://github.com/Gabb-c/pokenode-ts/commit/8ee4a959a10f09a798fbec072f973a8cb71cfe64))
* change regex for utility function ([03f7b6d](https://github.com/Gabb-c/pokenode-ts/commit/03f7b6d4a7d815a9ef6fbbdea526729424f93bb6))
* **client:** report a response to every caller ([9820e29](https://github.com/Gabb-c/pokenode-ts/commit/9820e296fcc12c5182dfbc526e4028556d59a041))
* hide credential logging ([00f0d8f](https://github.com/Gabb-c/pokenode-ts/commit/00f0d8f0e38f2305a293a67f695523cfde938408))

## [2.0.0](https://github.com/Gabb-c/pokenode-ts/compare/v1.19.0...v2.0.0) (2026-08-15)


### ⚠ BREAKING CHANGES

* ItemClient#listItemFilingEffects is renamed to listItemFlingEffects. The old name was a typo — the endpoint is item-fling-effect, after the move Fling — and no alias is kept, because 2.0 already asks callers to revisit their imports. Behavior is unchanged.
* axios and axios-cache-interceptor are no longer peer dependencies. cacheOptions is replaced by cache?: CacheStore | false, and logs?: boolean by logger?: Logger. ClientArgs is renamed ClientOptions. Failed requests reject with PokenodeError instead of AxiosError; match it with isPokenodeError rather than instanceof, which is false across a duplicated ESM/CJS copy of the class. MainClient no longer extends BaseClient. getResourceByURL throws a TypeError on a URL that names no endpoint under the base URL, where it previously issued a malformed request. ENDPOINTS.POKEMON_LOCATION_AREA is removed; it held a template, not an endpoint.

### Features

* add base getListURL method ([1b387c6](https://github.com/Gabb-c/pokenode-ts/commit/1b387c639229282934ca561c8661c911f20a2757))
* add currency client ([ed1a18f](https://github.com/Gabb-c/pokenode-ts/commit/ed1a18f968282b78abf6517c8878a2eea1409f8f))
* Add Showdown animated sprites ([02184a1](https://github.com/Gabb-c/pokenode-ts/commit/02184a11bb03608f7f1bd348137902cad19b6bf3))
* **clients:** add getResourceByURL for a custom base URL [#903](https://github.com/Gabb-c/pokenode-ts/issues/903) ([a76e5a0](https://github.com/Gabb-c/pokenode-ts/commit/a76e5a0481d00449bcbc48afd3e17a62fd4bf2a0))
* **clients:** refactor clients ([b3475f5](https://github.com/Gabb-c/pokenode-ts/commit/b3475f5781779d04f5d5a4920efd28ce4006a152))
* **models:** change from interface to type ([e2aa37c](https://github.com/Gabb-c/pokenode-ts/commit/e2aa37cd7f0755d5cb6692683cfa82cbdf63be44))
* **models:** update pokemon typings ([b74341a](https://github.com/Gabb-c/pokenode-ts/commit/b74341aede5204b2eb62304205765db54b36fc15))
* new build and release system ([1ed23bf](https://github.com/Gabb-c/pokenode-ts/commit/1ed23bfffdba17e91167a55c05c3025dfcdc82c6))
* refactor berry client ([eb2e30d](https://github.com/Gabb-c/pokenode-ts/commit/eb2e30d0ae2d2ae9c24c09e8b7813f6933826c29))
* replace axios with native fetch ([88ca8d5](https://github.com/Gabb-c/pokenode-ts/commit/88ca8d599ba6d66d44852c17fa776619a693dfbf))
* replace axios with native fetch ([a2f3c24](https://github.com/Gabb-c/pokenode-ts/commit/a2f3c24a33a245255ee143c66209000b0dff9db0))
* update evolution and pokemon typings ([f3a6086](https://github.com/Gabb-c/pokenode-ts/commit/f3a6086419a87066dcb213595ed207a6b088fe2d))


### Bug Fixes

* **base:** change base url enum to as const ([25e1be1](https://github.com/Gabb-c/pokenode-ts/commit/25e1be1ee88f7fc87f0fa87b1f5e6f52ff537f5f))
* **base:** fix get resource ([fa6576a](https://github.com/Gabb-c/pokenode-ts/commit/fa6576a37f7d41e1a483fcb0b26a77dbc07bb540))
* **build:** tsdown config ([be56498](https://github.com/Gabb-c/pokenode-ts/commit/be564982314afe4103a09bdf6dc35ddbeba9d3c1))
* **ci:** remove tsc lint from ci ([cea9117](https://github.com/Gabb-c/pokenode-ts/commit/cea9117c64d0f21487f41064f302dfa7acbecabf))
* **clients:** remove unused axios typings ([55d3aa8](https://github.com/Gabb-c/pokenode-ts/commit/55d3aa8aaacffaa59190cede57095baca6d89304))
* **clients:** revert usage of URLSearchParams [#839](https://github.com/Gabb-c/pokenode-ts/issues/839) ([c92e365](https://github.com/Gabb-c/pokenode-ts/commit/c92e3655cae153d4569c2f0ccdb4351aa8166cdf))
* **constants:** remove enums for readonly consts ([483252a](https://github.com/Gabb-c/pokenode-ts/commit/483252a39dd277c4a6d7cd1389551e9a18d4bf86))
* **lint:** replace rome for biome ([a6c2cff](https://github.com/Gabb-c/pokenode-ts/commit/a6c2cff5523c38f847048dceeeb71a4bb97107c6))
* **models:** add version to FlavorText interface ([793f266](https://github.com/Gabb-c/pokenode-ts/commit/793f2663539a7f1a48b5022ff575011d108c0757))
* pin nodejs version ([b410640](https://github.com/Gabb-c/pokenode-ts/commit/b410640e4fca87c108e9a2b83628b855f475377f))
* typo ([0c13ada](https://github.com/Gabb-c/pokenode-ts/commit/0c13ada2924bfc6d36689e673e61fd1d4d45649e))
* typo ([9bc9076](https://github.com/Gabb-c/pokenode-ts/commit/9bc90762a9f32236a51ba92639bc9521ca0a5753))


### Documentation

* overhaul documentation and .github ([6621101](https://github.com/Gabb-c/pokenode-ts/commit/66211016dd7df2ad7d56fe538022d55b5ae2f2f3))
