{
   "image" : null,
   "title" : "Perl string functions - concatenate substring and split",
   "authors" : [
      "David Farrell"
   ],
   "categories" : "development",
   "draft" : false,
   "tags" : [
      "operator",
      "string",
      "syntax",
      "old_site"
   ],
   "slug" : "8/2013/3/31/Perl-string-functions---concatenate-substring-and-split",
   "description" : "Perl has many string functions, let's take a look at a some of the most common ones: concatenate, substring and split.",
   "date" : "2013-03-31T23:04:34"
}


Perl has many string functions, let's take a look at a some of the most common ones: concatenate, substring and split.

### Concatenate

Concatenate strings by inserting a fullstop (.) operator between them. Perl will automatically 'stringify' scalar variables that were initialised as a number.

``` prettyprint
# declare and concatenate two strings
my $joke = 'A horse walks ' . 'into a bar.'; # A horse walks into a bar.
# Concatenate two scalars
my $meat  = 'ham';
my $bread = 'sandwich';
my $lunch = $meat . $bread; # hamsandwich

# Concatenate scalars initialised as numbers
my $hour        = 6;
my $minutes     = 30;
my $time_string = $hour . ':' . $minutes; # 6:30
```

### Substring

Substring extracts and returns a sub-set of an existing string. It takes up to four arguments: the expression to substring, the offset from where to start the substring, the length of the substring and a replacement string. If the length is omitted the substring will run to the end of input expression.

``` prettyprint
# substr(expression, offset, [length], [replacement])
my $joke            = 'A horse walks into a bar.';
my $animal          = substr($joke, 2, 5); # horse
my $favourite_place = substr($joke, -4); # bar.

# Extract a substring and replace the substring in the original string
my $verb        = substr($joke, 8, 5, 'runs'); # walks
print $joke; # A horse runs into a bar.
```

The [perldoc](http://perldoc.perl.org/functions/substr.html) page for substr has many more useful examples.

### Split

The split function divides an input string into a list of substrings using a split pattern, and an (optional) limit on the number of split fields. If the input expression is omitted, Perl will use $\_.

``` prettyprint
# split(pattern, [expression], [number_of_fields])
my $sentence       = 'A horse walks into a bar.';
my @words          = split(' ', $sentence); # A,horse,walks,into,a,bar

my $fullname       = 'Mr Stephen Doyle';

# Limit the split to two fields
my @title_and_name = split(' ', $fullname, 2); # Mr,Stephen Doyle
```
