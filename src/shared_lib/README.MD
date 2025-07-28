this is for uploading usable fucntions to be used in different pipelines easy:


cd src/shared_lib
python setup.py sdist


pip install / uv add twine

innan upload måste du hämtat service key som kommer från terraform in här för att lättast undåg 401 access

upload 
uv run twine upload --repository-url \
  https://europe-west1-python.pkg.dev/test-project-btc-bros-1/my-repo-idd/ \
  -u _json_key -p "$(cat key.json)" dist/* 

för att se mer vad som hnder loggar tillbaka:
uv run twine upload --repository-url \
  https://europe-west1-python.pkg.dev/test-project-btc-bros-1/my-repo-idd/ \
  -u _json_key -p "$(cat key.json)" dist/* --verbose