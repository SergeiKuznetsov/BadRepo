# Пример репозитория, который не клонируется под Windows

После клонирования получим ошибку: unable to checkout working tree.

Причина в имени папки с точкой в конце. 

Лечится командой:

``
git filter-repo --force --filename-callback 'return re.sub(b''(.+)\\./'', b''\\1/'', filename)'
``
