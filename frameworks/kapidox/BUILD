source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

python -m build --wheel &&

prepare_install &&
python -m installer dist/*.whl
