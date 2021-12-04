# omoide-digest

[![Build Status](https://github.com/IgorZyktin/omoide-digest/workflows/test/badge.svg?branch=master&event=push)](https://github.com/IgorZyktin/omoide-digest/actions?query=workflow%3Atest)
[![codecov](https://codecov.io/gh/IgorZyktin/omoide-digest/branch/master/graph/badge.svg)](https://codecov.io/gh/IgorZyktin/omoide-digest)
[![Python Version](https://img.shields.io/pypi/pyversions/omoide-digest.svg)](https://pypi.org/project/omoide-digest/)
[![wemake-python-styleguide](https://img.shields.io/badge/style-wemake-000000.svg)](https://github.com/wemake-services/wemake-python-styleguide)

Загрузчик контента для проекта Omoide.

## Что делает

Предоставляет консольные инструменты для анализа исходных данных и их загрузки
в базу Omoide.

Имеет три базовых операции:

1. [Digest](omoide_digest/digest/README.md) - пройтись по пользовательским файлам и собрать с них всю метаинформацию.
2. [Convert](omoide_digest/convert/README.md) - сохранить или скопировать пользовательские файлы в каталоги, из которых с ними потом сможет работать Omoide.
3. [Sync](omoide_digest/sync/README.md) - синхронизировать локальную базу данных с базой данных приложения.

## Почему именно так

Digest является отдельным компонентом, его наличие не требуется для работы 
приложения, он имеет свои специфические зависимости. Было решено вынести его в 
отдельный репозиторий. Основная идея его работы - порождать такие артефакты из 
пользовательских данных, которые позволят заполнить пустую базу данных или 
исправить повреждённую. 

Он сохраняет промежуточные представления в виде sqlite баз, каждое из которых 
по сути является полноценной базой данных сервера. Однако вспомогательная 
информация при операции sync в основную базу не попадает.

## License

[MIT](https://github.com/IgorZyktin/omoide-digest/blob/master/LICENSE)

## Credits

This project was generated with [`wemake-python-package`](https://github.com/wemake-services/wemake-python-package). Current template version is: [2e71727d0e666fc42c17f29897b1a59191c06428](https://github.com/wemake-services/wemake-python-package/tree/2e71727d0e666fc42c17f29897b1a59191c06428). See what is [updated](https://github.com/wemake-services/wemake-python-package/compare/2e71727d0e666fc42c17f29897b1a59191c06428...master) since then.
