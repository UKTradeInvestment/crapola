# Convert Excel HTML files to CSV

Python 3 required.

Create a report in Microsoft Dynamics and click "Export to Excel". Grab the
file created that ends in ``.xls`` but has headers that look like:

    <html xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:x="urn:schemas-microsoft-com:office:excel" xmlns="http://www.w3.org/TR/REC-html40"><head><meta http-equiv=Content-Type content="text/html; charset=windows-1252"><meta name=ProgId content=Excel.Sheet><style type="text/css">
            <!--table

Use Python to convert the file (this will dump it to stdout):

    python excel/process.py [file downloaded]

The output can be streamed into a file of your choice:

    python excel/process.py [file downloaded] > [csv filename]

The file at location ``csv filename`` should now contain a CSV version of the
data exported from Dynamics.

## Tests

Tests need some extra tools, so use a virtual environment and install
requirements.

    virtualenv venv --python=python3
    . venv/bin/activate
    pip install -r requirements-test.txt

Run tests:

    py.test excel/tests.py
    flake8 excel
