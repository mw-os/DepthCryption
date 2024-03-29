# DepthCryption
![Windows](https://img.shields.io/badge/Windows-ff3f0f?style=for-the-badge&logo=windows&logoColor=ffffff)
![Linux](https://img.shields.io/badge/Linux-55ff55?style=for-the-badge&logo=linux&logoColor=777777)
![Apple](https://img.shields.io/badge/Apple-0077EE?style=for-the-badge&logo=Apple&logoColor=ffffff) + 
![Python](https://img.shields.io/badge/Python-3.9%20%7C%203.10%20%7C%203.11%20%7C%203.12-DFDB58?style=for-the-badge&logo=python&logoColor=CCC95B)


[![Visitors](https://api.visitorbadge.io/api/combined?path=https%3A%2F%2Fgithub.com%2Fmw-os%2FDepthCryption&label=Views&countColor=%777777a&style=flat)](https://visitorbadge.io/status?path=https%3A%2F%2Fgithub.com%2Fmw-os%2FDepthCryption)

![DC_LOGO_small](https://github.com/mw-os/DepthCryption/assets/155395934/deb19578-6080-43d2-b5a2-0c8fbff23f7a)

**DepthCryption** is bleeding edge encryption package that offers a novel approach to encryption that has never been seen before, offered through incredibly easy to use functions with an impressive suite of features.

- [Highlights](#Highlights)
- [Initial setup](#initial-setup)
- [Usage](#usage)
- [FAQ](#faq)
- [Contributing](#contributing)


## Highlights

Key highlights of DepthCryption include: 

Unhackable.
Quantum proof.
Zero dependencies.
Works on all common operating systems.
Works on all modern versions of python.
Encrypted data can intrinsically expire at a user defined time, ensuring expired encrypted data is never recoverable.
Crack tables / hash tables / lookup maps (E.G. Rainbow Table) can never be used to hack data encrypted with DepthCryption, because outputs are guaranteed to be non-unique.
Knowledge or communication of a passwords a thing of the past with optional intrinsic passkeys.
With optional use of passwords or keys, there is never the possibility of a stolen password/key jeopardizing encrypted data.
Encrypts every type of file, directory/folder, and almost every type of object in python.
The optional "decryption failure probability" feature allows users to define a probability of successful decryption, deterring would-be hackers from knowing why hacking attempts are failing.
Pure python, no C /C++/FORTRAN code to be compiled.
Major points of backwards-compatibility baked in to the existing framework.
Encrypted data represented as common Latin ASCII values, ensuring maximum transportability of encrypted data.


### *Unhackable* and *Quantum proof* are huge claims?

All kinds of encryption attack vectors have one thing in common, that they have some sort of rudimentary idea about how the type of encryption works or the rules that it operates by. With some ideas of those rule, advances research, large scale computing, or social engineering can all be used to break an encryption. DepthCryption stands uniquely outside of this paradigm, by not play by any standard handful of rules. Instead, DepthCryption can dynamically switch between 3,838,000,000,000 sets of default rules, at the time of this beta release (users can expand this). Creating a system to crack 3.8 Trillion different rules sounds like a gigantic pain, but theoretically doable if you just know which one to use at which time. The trouble is that the DepthCryption program has no idea which set of rules it uses to encrypt at any given time. To get around this a hacker would theoretically have to develop a crackable reproduction of DepthCryption that simultaneously ran between 3.8 Trillion sets of rules. The issue then becomes that your encrypted data is non-unique and can be represented in any number of ways. If a hacker stole your DepthCryption encrypted data they must then run different combinations of passwords and internal keys through all 3.8 Trillion rule sets. But since DepthCryption outputs are non-unique, the different combinations of passwords and keys a hacker tries could all successfully decrypt into something... But what is the right thing? Each attempt of running through all the 3.8 Trillion rules could produce up to 3.8 Trillion results, a simple test of 10,000 password and key combination could produce up to 
38 Quadrillion 'successful' decryption outputs! 

It is the extremely high hurdle of simultaneously cracking 3.8 Trillion sets of rules with the unknowability of whether hacked decrypted data is even what you even encrypted in the first place. If you want to monkey-patch DepthCryption, the number of rules can easily exceed 154,759,000,000,000,000,000 (155 thousand quadrillion rules). Future planned features will allow the possible number rules to exceed the number of atoms in the universe!

### Links

- GitHub: https://github.com/mw-os/DepthCryption
- PyPI: https://pypi.org/project/DepthCryption/

![DC_LOGO_BLACK](https://github.com/mw-os/DepthCryption/assets/155395934/8bcb363a-a151-4288-b5cb-a90d0a3bac86)

## Initial setup

1. Download via pip:
    ```
    python -m pip install depthcryption
    ```

2. Import the package into your module:
    ```
    import depthcryption as dc
    ```

3. Run your first encryption and decryption test:
    ```
    import depthcryption as dc
    original_data = ['some test stuff', {5}, (5.1, 5.2)]
    encrypted_data = dc.encrypt(original_data)
    print(f'The resulting encrypted data is: {encrypted_data}')
    decrypted_data = dc.decrypt(encrypted_data)
    print(f'Decryption matches original: {original_data==decrypted_data}')
    ```


## Usage
 
### Getting started with DepthCryption

There are two functions that DepthCryption offers: 

- encrypt
- decrypt

No other complicated bells or whistles or any other considerations, you do not need to have any other external package installed to run the encrypt or decrypt functions! To learn more about the features and parameters of these functions, just use the __*help*__ function on them at anytime. While they do offer an extremely wide number of features and options, the usage of these function can be just as simple as running them with their defaults.

Please note: at the time of this current beta release the core methodologies of the package have not been fully optimized yet and have an exponential runtime. 1 MB data objects for encryption take roughly 45 seconds while 2 MB data objects take roughly 110 seconds*.

__*It is therefore recommended to only encrypt objects under 2 MB at a time to ensure a reasonable runtime.__



### Usage of dc.encrypt
```
>>> import depthcryption as dc
>>> help(dc.encrypt)
Help on function encrypt in module DepthCryption.user_functions:

encrypt(*args: object, **kwargs: object) -> str
    The DepthCryption encrypt function is the main encryption function API.


    ----------------------- example usage -----------------------

    >>> original_obj_ = ['test list', 1, {2}, 3.0]
    >>> encrypted_obj_ = encrypt(original_obj_)
    >>> print(f"Encrypting {original_obj_} has resulted in {encrypted_obj_}")


    ---------------------- long description ----------------------

    The encrypt function takes an input in and following an unknown
    number of layers of unknown types of encryption methodologies
    with an unknown amount of complexity will produce an outgoing
    encrypted output of all of its provided arguments as a string.
    Almost all pythonic objects, files and directories can be
    given to the encryption function individually or simultaneously.


    ---------------------- function inputs ----------------------

    --------- target encryption objects ---------

    :param args: Any number of objects to encrypt can be entered
        as positional arguments into the encrypt function.
        All inputs must either be pickleable OR file paths to
        either files or directories to encrypt. If an incoming
        argument is a pathlib object or a string, DepthCryption
        will check to see if that file or directory exists.
        If the string or pathlib object does exist then its
        contents are read into the program.

    :type args: object

    -------------- program features --------------

    :param compression: An optional integer/string ('lzma',
        'zip') keyword argument that specifies what compression
        technique DepthCryption uses to internally compress
        data.

    :type compression: str or int

    :param decryption_complexity: An optional integer/string
        ('low', 'medium', 'high', 'extreme') keyword argument
        that specifies how difficult it is for DepthCryption
        to evaluate this object for decryption. Higher values
        are more secure, but demand more resources at runtime.

    :type decryption_complexity: str or int

    :param encryption_complexity: An optional integer/string
        ('low', 'medium', 'high', 'extreme') keyword argument
        that specifies how "encrypted" a DepthCryption output
        is. Higher values are more secure, but demand more
        resources at runtime.

    :type encryption_complexity: str or int

    :param probability: An optional integer keyword argument
        input for the probability of successful decryption.
        If this is set to 2, there is a 1/2 probability that
        decryption will be successful each time it is attempted;
        if this is set to 7, there is a 1/7 probability that
        decryption will be successful each time it is attempted.

    :type probability: int

    :param save_file: An optional string or pathlib object
        keyword argument that specifies the file that the
        resulting encrypted data is saved to.

    :type save_file: str or pathlib.PurePath

    -------------- encryption keys --------------

    :param key_files: An optional string or a pathlib object
        keyword argument input (of either a directory or file)
         that will use the data of the specified files/file
         structure as an encryption key.

    :type key_files: str or pathlib.PurePath

    :param key_ip: An optional boolean keyword argument
        input that will use the public ip of this current device
        as an encryption key, only IPv4 supported at this time.
        --> NOTE: A public IP address may change over time,
        --> depending on: your internet provider, connecting device,
        --> vpn configurations, if your device has a dynamic IP
        --> setting, or any other number network
        --> settings/configurations.

    :type key_ip: bool

    :param key_os: An optional boolean keyword argument
        input that will use the operating system identifier of
        this current device as an encryption key.

    :type key_os: bool

    :param key_py: An optional boolean keyword argument
        input that will use the python version metadata of this
        current interpreter as an encryption key.

    :type key_py: bool

    :param key_time: An optional keyword argument input of
        when the encrypted object can no longer be decrypted,
        trying to decrypt an object after the time of
        expiry will cause failure. Can either be specified
        as a unix timestamp or as a list of local dates/times
        in [yyyy, MM, dd, hh, mm, ss] format,
        e.g. [2015, 10, 21, 7, 28, 0], or [1985, 10, 26],
        or [1955, 11], ect... Expiration occurs at the
        first millisecond after the specified key_time.

    :type key_time: float or int or list[int] or list[float] or
        list[int or float] or datetime.datetime

    :param key_url: An optional string or list
         keyword argument input (list containing url strings)
         that will scrape the data on provided website's page
         and us it as an encryption key.
         --> NOTE: Webpages can change at any time for any
         --> reason; even webpages that appear the same
         --> to the eye may have small changes in their data,
         --> metadata, or how that data is delivered, and this
         --> will cause decryption to fail in the case that
         --> the scraped data is not exactly identical.
         --> Use cautiously.

    :type key_url: str or list[str] or tuple[str] or set[str]

    :param user_key: An optional keyword argument input where
        the user can specify their own key or password for
        DepthCryption to use. All python objects are acceptable,
        so long as they are pickleable.
        --> NOTE: The user MUST provide this identical value
        --> again EVERY single time that this object is decrypted.
        --> If this value is not reproduced identically at the
        --> time of decryption, decryption cannot occur.

    :type user_key: object

    -------------------------- raises --------------------------

    :raises AssertionError: Strong type checking failure. One of
        the inputs (also described in the corresponding
        exception message) is not of the supported input types
        of the corresponding function input (also described in
        the exception message). Checking that the correct types
        of input(s) remediates this exception.

    :raises EncryptionException: User provided an input of the
        correct type, and that the program can access, but for
        various reasons (also described in the exception
        message) the program cannot pass along the user
        provided input. Reviewing the exception message to
        understand why the program cannot use the input can
        help remediate this exception.

    :raises InterpreterException: The current runtime interpreter
        is currently using a version of python that the package
        is not able to run from.

    :raises UserException: User provided an input of the correct
        type, but for various reasons (also described in the
        exception message) the program cannot access the
        provided input. Using the exception message to determine
        the access issue and its causes, this exception can be
        remediated.


    ------------------------- returns -------------------------

    :returns: An encrypted object as a string. If multiple objects
        are given to the encryption function positional arguements
        in a single functional call then they are all encrypted
        together and wholly represented in the outgoing string.
        Optionally saves an outgoing encrypted object if the
        save_file input is specified.

    :rtype: str

>>>
```

### Usage of dc.decrypt

```
>>> import depthcryption as dc
>>> help(dc.decrypt)
Help on function decrypt in module DepthCryption.user_functions:

decrypt(*args: Union[str, pathlib.PurePath], **kwargs: object) -> object
    The DepthCryption decrypt function is the main decryption function API.


    ----------------------- example usage -----------------------

    >>> original_obj_ = ['test list', 1, {2}, 3.0]
    >>> encrypted_obj_ = encrypt(original_obj_)
    >>> decrypted_obj_ = decrypt(encrypted_obj_)
    >>> print(f"Objects match: {original_obj_==decrypted_obj_}")


    ---------------------- long description ----------------------

    The decrypt function takes in encryption strings that have been
    created by the encrypt function and produces the original python
    objects, files, and/r directories that have originally been
    encrypted. The decrypt function can take in the strings themselves
    as a native python string, and it can also take in file paths to
    files containing these strings.


    ---------------------- function inputs ----------------------

    --------- target decryption objects ---------

    :param args: Any number of objects to decrypt can be entered
        as positional arguments into the decrypt function.
        All inputs must either be previously encrypted strings OR
        file paths that contain previously encrypted strings.
        If an incoming argument is a pathlib object or a string,
        DepthCryption will check to see if that file or directory
        exists. If the string or pathlib object does exist then its
        contents are read into the program.

    :type args: str or pathlib.PurePath

    -------------- program features --------------

    :param return_paths: An optional bool keyword argument that
        specifies if the file paths to the decrypted objects
        are also returned with the objects. If True, the paths
        will be returned in a separate list in the same
        respective order as the decrypted items.

    :type return_paths: Strings or path objects.

    :param save_dir: An optional string or pathlib object
        keyword argument that specifies where to save decrypted
        items. The specified directory must exist. If the
        decrypted object is a previously encrypted directory
        the directory will be placed into here. If the decrypted
        object is an encrypted object that was not an encrypted
        file or directory, it will be converted to a string with
        a unique file name created just for it.

    :type save_dir: str or pathlib.PurePath

    -------------- encryption keys --------------

    :param key_files: If the key_files key was used to encrypt
        data, but that path does not currently exist on the
        decrypting device then the provided path can be
        overwritten using key_files at the time of decryption.
        If only a single file was used when encrypting with
        key_files then that file must be placed alone into the
        updated key_files directory currently being used for
        decryption.

    :type key_files:  str or pathlib.PurePath

    :param user_key: An optional keyword argument input where
        the user can specify their own key or password for
        DepthCryption to use. If there was a user specified
        password/key object that was used to encrypt the
        current input it must be supplied here.

    :type user_key: object


    -------------------------- raises --------------------------

    :raises AssertionError: Strong type checking failure. One of
        the inputs (also described in the corresponding
        exception message) is not of the supported input types
        of the corresponding function input (also described in
        the exception message). Checking that the correct types
        of input(s) remediates this exception.

    :raises InterpreterException: The current runtime interpreter
        is currently using a version of python that the package
        is not able to run from.

    :raises DecryptionException: User provided an input of the
        correct type, and that the program can access, but for
        various reasons (also described in the exception
        message) the program cannot pass along the user
        provided input. Reviewing the exception message to
        understand why the program cannot use the input can
        help remediate this exception.

    :raises UserException: User provided an input of the correct
        type, but for various reasons (also described in the
        exception message) the program cannot access the
        provided input. Using the exception message to determine
        the access issue and its causes, this exception can be
        remediated.


    ------------------------- returns -------------------------

    :returns: The decrypted object(s). If return_paths is set
        to True, the associated file paths are also returned
        if the decrypted object(s) are written to disk. Objects
        that were encrypted directly from files are automatically
        written back out to their original locations or where
        ever is specified in the save_dir variable. If neither
        of these are viable DepthCryption attempts to make a new
        folder on the desktop and save the respective files there

    :rtype: object or list[object] or object and list[str] or
        list[object] and list[str]

>>>
```
## FAQ

### What can I encrypt using DepthCryption? 

Almost all things in python, paths to files and directories are also valid inputs if you would like to encrypt them! DepthCryption relies on pickling and unpickling data and this presents the only limitation. Since files and directories are loaded in directly as byte data there is no limitations on data outside of python. 

### What is the *key_os* feature when encrypting? 

Almost every single modern electronic object has its own unique identifier that distinguishes it from all other modern electronic objects. All of our operating systems have one too, and they never change! Setting *key_os* to **True** means that an encrypted data can **only be decrypted on your current computer**. Please note though that if you're extra cool and have multiple operating systems on your computer, each of them will have a different identifier and data encrypted on one OS will not be able to be decrypted on another OS despite them sharing hardware.

### What is the *key_time* feature and how could my data be set to expire? 

When encrypting your data with the *key_time* feature the date and time that you put in are used in a big math problem that uses complex hyperbolic calculus to change how your data has been encrypted. When you try to encrypt that data at a later time the current time is put into the previously established complex hyperbolic function and returns new results. These new results work on attempting to decrypt the data, but if it is past the expiration time then the results will no longer work with the function! Please note though, that when specifying the *key_time* as a local date time, the expiration occurs on the first nanosecond into that time; I.E. a key_time=[2025,5] will expire in the first nanosecond of May 2025, while [2015, 10, 21, 7, 28, 11]  would expire in the first nanosecond into the eleventh second of 7:28 on 2015 May 21st.  

### What is the *probability* feature when encrypting?

This feature allows for an otherwise successful decryption to fail with a certain probability of 1/probability. If you set probability to 3 then decryption would only be successful 1/3 of the times it is attempted, and fail 2/3 of the times. Or if you set probability to 10 then decryption would only be successful 1/10 of the time, but fail to decrypt 9/10 times you ran the dc.decrypt function. This feature does not damage or interact with any of the encrypted data and only interacts with the DepthCryption code. Try it for yourself with a probability of 2! A small warning will appear to tell you how many decryption attempts you might need to have a 99% of decrypting successfully at least once, you may be surprised by how often the program is either crashing or producing a successful decryption! 

### What is the *key_files* feature when decrypting?

The *key_files* for decryption is the exact same as the one used for encryption, but it offers you the chance to update the current location of the file or directory that is being used as a key. This can be useful if you are sharing encrypted data with someone else and do not want to make passwords. Instead, you can just use the key_files option with a file or directory, and send that file or directory to another person so that they can use it at the time of decryption. Thus, completely avoiding the need for traditional passwords or retaining otherwise obvious passkeys. 

### What license is DepthCryption released under? 

DepthCryption is release under GNU GPL V3. 

### Plans for future updates? 

Current planned updates include features for:
- Optimizations to internal logics
- Multithreaded encryption for faster and more secure encryption 
- Support for concurrent i/o processes
- Full build outs and easy to use CLI options
- Expand current selections of encryption logics

## Contributing

If you find a bug, [please report it!](https://github.com/mw-os/DepthCryption/issues/new?assignees=&labels=bug)

If you have additional ideas that you would like to see in DepthCryption, [please request them!](https://github.com/mw-os/DepthCryption/issues/new?assignees=&labels=enhancement)


GitHub Stats ![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/mw-os/DepthCryption/total?style=flat&label=Downloads&labelColor=#777777&color=ffffff)

PyPI Stats ![PyPI downloads](https://img.shields.io/pypi/dm/DepthCryption?style=flat&labelColor=black&color=white)

