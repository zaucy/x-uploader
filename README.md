## HTML Uploader Element
This web component adds a new element, the x-uploader. This element gives you the ability to just throw down an uploader whereever you want. It has drag and drop support and some file type and size enforcing.

When the x-uploader element contains content a `<hr>` element will be placed inbetween the content and the file selecting area.

### Attributes
**type**
>This is the exact same as the input elements [accept](https://developer.mozilla.org/en/docs/Web/HTML/Element/Input#attr-accept) attribute and has nearly the same effect.

**maxsize**
> The maxsize limits the size of the file being uploaded. If multiple files are selected the maxsize applies to each file. Note that this isn't fool proof, there are situations where the user may be able to bypass this so the server should double check it's within the limits. The value will be parsed as an integer representing the maxsize in bytes. Alternatively you may append a different size other than byte:
  - **B** Represents a [Byte](http://en.wikipedia.org/wiki/Byte). (this is default)
  - **b** Represents a [bit](http://en.wikipedia.org/wiki/Bit).
  - **KB** Represents a [metric kilobyte](http://en.wikipedia.org/wiki/Kilobyte).
  - **kb** represents a [metric kilobit](http://en.wikipedia.org/wiki/Kilobit).
  - **kB** or **KiB** represents a [IEC kibibyte](http://en.wikipedia.org/wiki/Kibibyte).
  - **MB** Represents a [metric megabyte](http://en.wikipedia.org/wiki/Megabyte).
  - **mb** represents [metric megabit](http://en.wikipedia.org/wiki/Megabit).
  - **mB** or **MiB** represents a [IEC   mebibyte](http://en.wikipedia.org/wiki/Mebibyte).
  <br>... etc. all the way to [yottabyte](http://en.wikipedia.org/wiki/Yottabyte), [yottabit](http://en.wikipedia.org/wiki/Yottabit) and [yobibyte](http://en.wikipedia.org/wiki/Yobibyte).

**onupload**
> The callback when a file is accepted for upload. If the value is a string a new function will be created with the string as it's body. Note: reassignment of this attribute will remove the old callback.

## Example
```html
<x-uploader type="image/*" maxsize="2MB">
  Upload images to be used on this site!
</x-uploader>
```
The result should look similar to the box below.

<div style="border: dashed 4px; padding: 8px">
Upload images to be used on this site!
<hr>
<div style="text-align: center">
<div>
Drag and drop your files here
<br>
OR
</div>
<button>Select Files</button>
<div>Maximum upload file size: 2MB.<br>
Image files only.</div>
</div>
</div>
