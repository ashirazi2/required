Required - a utility to require all files in a directory
==

Required provides the ability to **require** all files within a
**d**irectory, with options for file inclusion/exclusion based on pattern
matching, as well as recursive descent. An array of all the files that were
loaded ('require' only loads a file the first time) are returned.

Quick start
--

First pull in the 'required' module:
>    require 'required'

To pull in all ruby files in a directory (this excludes subdirectories):
>    required "some/path/to/dir"

Same as before, but require the files in reverse alphanumeric order:
>    required "some/path/to/dir", :sort => lambda { |x, y| y <=> x}

To pull in files from multiple directories:
>    required ["some/path/to/dir", "another/path/another/dir"]

Or to recurse through subdirectories, requiring all files along the way:
>    required "lib", {:recurse => true}

Same as before, but exclude ruby files tagged as "_old":
>    required "lib", {:recurse => true, :exclude => /_old/}  
>    # Will not require "lib/extensions/string_old.rb"

Same as before, but only require ruby files tagged with "_new":
>    required "lib", {:recurse => true, :include => /_new/}

Installing with RubyGems
--

A Gem of Required is available at gemcutter.org.  You can install it with:
>    gem install required

Running the tests
--

Testing Required requires the shoulda testing framework:
    gem install shoulda

There is one rake-based test task:
    rake test       runs all the tests

History
--

* 2010-03-31: First public release 0.1.x

Contact
--

Git repository (send Git patches to the mailing list):
* http://github.com/ashirazi/required

Thanks
--

I would like to thank Ryan Wilcox for coming up with the initial idea and
implementation of a convenience method for requiring everything in a directory
for a project we work on.

Copyright
--

Copyright (C) 2010 Arild Shirazi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to
deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Links
--

Required's RubyGems.org project:: <http://rubygems.org/gems/required>

Official Required repository:: <http://github.com/ashirazi/required>
