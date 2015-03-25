### about ###

'bdpy' faciliates programmatic access to [BorrowDirect](http://www.borrowdirect.org), an academic book-borrowing consortium.

_under development_

_( formatted in [markdown](http://daringfireball.net/projects/markdown/) )_

on this page...

- installation
- common usage
- notes
- license



### installation ###

- for now:

        $ pip install requests
        $ pip install git+git://github.com/birkin/borrowdirect.py.git@0.3-dev

- best to install a release version while it's under development; sometimes I check-in code that's not fully working

- todo: load to [pypi](https://pypi.python.org/pypi)

- one dependency: the awesome [requests](http://docs.python-requests.org/en/latest/) module



### common usage ###

(works)

    >>> from bdpy import BorrowDirect
    >>> settings = { u'UNIVERSITY_CODE': the_university_code, u'API_AUTHENTICATION_URL': the_authentication_url, u'API_AUTHORIZATION_URL': the_authorization_url }
    >>> bd = BorrowDirect( settings )
    >>> bd.run_auth_nz( a_patron_barcode )  # performs authN/Z & stores authentication-id
    >>> bd.AId  # authoriztion-id
    u'abc...'
    >>> bd.bd.authnz_valid
    True

(todo)

    >>> bd.search( the_isbn )  # output TBD

    >>> bd.request( the_isbn )  # output TBD



### notes ###

- instantiation is flexible
    - you can pass in a settings-module, or a settings-module-path, or nothing (but then set the class-attributes directly)
    - the patron-barcode can be included in settings
    - todo: if patron barcode is passed in, authNZ will kick off automatically, so you can get right to searching & requesting

- contact: birkin_diana@brown.edu



### license ###

The [MIT License](http://opensource.org/licenses/MIT) (MIT)

    Copyright (c) 2015 http://library.brown.edu/its/

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.



---