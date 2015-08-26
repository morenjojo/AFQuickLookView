# AFQuickLookView

AFQuickLookView is an extension for [AFNetworking](http://github.com/AFNetworking/AFNetworking/) that allows the display of remote files in a UIView subclass.

This is still in early stages of development, so proceed with caution when using this in a production application. Any bug reports, feature requests, or general feedback at this point would be greatly appreciated.

原作者很近没更新了，我来更新一下

## Example Usage

Add an instance of the AFQuickLookView to the view of you choosing:

``` objective-c
CGRect frame = CGRectMake(0, 100, 300, 300);
AFQuickLookView* quickLookView = [[AFQuickLookView alloc] initWithFrame:frame];
[self.view addSubview:quickLookView];
```

Trigger loading a remote document:

``` objective-c
NSString* fileURLString = @"http://bit.ly/xngAttPDF";
NSURL* fileURL = [NSURL URLWithString:fileURLString];
[quickLookView previewDocumentAtURL:fileURL success:^{
} failure:^(NSError *error) {
NSLog(@"Could not preview document. Error:%@", error);
}];

```

## Supported file formats

- iWork documents
- Microsoft Office documents (Office '97 and newer)
- Rich Text Format (RTF) documents
- PDF files
- Images
- Text files
- Comma-separated value (csv) files

## HTTP layer Details

In order for AFQuickLookView to work with remote files, the server response has to comply to one of these options: 

a) include a *Content-Type* header, e.g.:

```
Content-Type: application/pdf
```

b) include the right filename and extension in the *Content-Disposition* header, i.e.:

```
Content-Disposition: attachment;filename="examplefile.pdf"
```

## Contact

原作者：
XING AG

- https://github.com/xing
- https://twitter.com/xingdevs
- https://dev.xing.com

Claudiu-Vlad Ursache

- https://github.com/ursachec
- https://twitter.com/ursachec
- http://cvursache.com

update by：
- https://github.com/morenjojo

## License

AFQuickLookView is available under the MIT license. See the LICENSE file for more info.
