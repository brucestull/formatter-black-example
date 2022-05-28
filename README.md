# formatter-black-example

## Resources:
* https://black.readthedocs.io/en/stable/getting_started.html
* https://pypi.org/project/black/
* https://github.com/psf/black

## Prepare:
* Check for needed changes:  
`black .\black_test.py --diff --color`  
    ```
    (formatter-black-example) PS C:\Users\User\Programming\formatter-black-example> black .\black_test.py --diff --color
    --- black_test.py       2022-05-28 02:09:58.973138 +0000
    +++ black_test.py       2022-05-28 02:14:02.787135 +0000
    @@ -1,40 +1,61 @@
    from seven_dwwarfs import Grumpy, Happy, Sleepy, Bashful, Sneezy, Dopey, Doc
    -x = {  'a':37,'b':42,
    
    -'c':927}
    +x = {"a": 37, "b": 42, "c": 927}
    
    -x = 123456789.123456789E123456789
    +x = 123456789.123456789e123456789
    
    -if very_long_variable_name is not None and \
    - very_long_variable_name.field > 0 or \
    - very_long_variable_name.is_debug:
    - z = 'hello '+'world'
    +if (
    +    very_long_variable_name is not None
    +    and very_long_variable_name.field > 0
    +    or very_long_variable_name.is_debug
    +):
    +    z = "hello " + "world"
    else:
    - world = 'world'
    - a = 'hello {}'.format(world)
    - f = rf'hello {world}'
    -if (this
    -and that): y = 'hello ''world'#FIXME: https://github.com/psf/black/issues/26
    -class Foo  (     object  ):
    -  def f    (self   ):
    -    return       37*-2
    -  def g(self, x,y=42):
    -      return y
    -def f  (   a: List[ int ]) :
    -  return      37-a[42-u :  y**3]
    -def very_important_function(template: str,*variables,file: os.PathLike,debug:bool=False,):
    +    world = "world"
    +    a = "hello {}".format(world)
    +    f = rf"hello {world}"
    +if this and that:
    +    y = "hello " "world"  # FIXME: https://github.com/psf/black/issues/26
    +
    +
    +class Foo(object):
    +    def f(self):
    +        return 37 * -2
    +
    +    def g(self, x, y=42):
    +        return y
    +
    +
    +def f(a: List[int]):
    +    return 37 - a[42 - u : y**3]
    +
    +
    +def very_important_function(
    +    template: str,
    +    *variables,
    +    file: os.PathLike,
    +    debug: bool = False,
    +):
        """Applies `variables` to the `template` and writes to `file`."""
        with open(file, "w") as f:
    -     ...
    +        ...
    +
    +
    # fmt: off
    custom_formatting = [
        0,  1,  2,
        3,  4,  5,
        6,  7,  8,
    ]
    # fmt: on
    regular_formatting = [
    -    0,  1,  2,
    -    3,  4,  5,
    -    6,  7,  8,
    -]
    \ No newline at end of file
    +    0,
    +    1,
    +    2,
    +    3,
    +    4,
    +    5,
    +    6,
    +    7,
    +    8,
    +]
    would reformat black_test.py

    All done! ✨ 🍰 ✨
    1 file would be reformatted.
    ```

* Make changes:  
`black .\black_test.py`  
`cat .\black_test.py`  
    ```
    (formatter-black-example) PS C:\Users\User\Programming\formatter-black-example> cat .\black_test.py  
    from seven_dwwarfs import Grumpy, Happy, Sleepy, Bashful, Sneezy, Dopey, Doc

    x = {"a": 37, "b": 42, "c": 927}

    x = 123456789.123456789e123456789

    if (
        very_long_variable_name is not None
        and very_long_variable_name.field > 0
        or very_long_variable_name.is_debug
    ):
        z = "hello " + "world"
    else:
        world = "world"
        a = "hello {}".format(world)
        f = rf"hello {world}"
    if this and that:
        y = "hello " "world"  # FIXME: https://github.com/psf/black/issues/26


    class Foo(object):
        def f(self):
            return 37 * -2

        def g(self, x, y=42):
            return y


    def f(a: List[int]):
        return 37 - a[42 - u : y**3]


    def very_important_function(
        template: str,
        *variables,
        file: os.PathLike,
        debug: bool = False,
    ):
        """Applies `variables` to the `template` and writes to `file`."""
        with open(file, "w") as f:
            ...


    # fmt: off
    custom_formatting = [
        0,  1,  2,
        3,  4,  5,
        6,  7,  8,
    ]
    # fmt: on
    regular_formatting = [
        0,
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
    ]
    (formatter-black-example) PS C:\Users\User\Programming\formatter-black-example> cat .\black_test.py
    from seven_dwwarfs import Grumpy, Happy, Sleepy, Bashful, Sneezy, Dopey, Doc

    x = {"a": 37, "b": 42, "c": 927}

    x = 123456789.123456789e123456789

    if (
        very_long_variable_name is not None
        and very_long_variable_name.field > 0
        or very_long_variable_name.is_debug
    ):
        z = "hello " + "world"
    else:
        world = "world"
        a = "hello {}".format(world)
        f = rf"hello {world}"
    if this and that:
        y = "hello " "world"  # FIXME: https://github.com/psf/black/issues/26


    class Foo(object):
        def f(self):
            return 37 * -2

        def g(self, x, y=42):
            return y


    def f(a: List[int]):
        return 37 - a[42 - u : y**3]


    def very_important_function(
        template: str,
        *variables,
        file: os.PathLike,
        debug: bool = False,
    ):
        """Applies `variables` to the `template` and writes to `file`."""
        with open(file, "w") as f:
            ...


    # fmt: off
    custom_formatting = [
        0,  1,  2,
        3,  4,  5,
        6,  7,  8,
    ]
    # fmt: on
    regular_formatting = [
        0,
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
    ]
    ```
