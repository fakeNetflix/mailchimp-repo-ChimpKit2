*** THIS PROJECT IS DEPRECATED ***

Please use [ChimpKit 2](http://github.com/mailchimp/chimpkit2) instead!

ChimpKit
---------
API wrapper for the [mailchimp.com](http://mailchimp.com/api "MailChimp API") API.


###Install & Setup
    
Get your API key from [http://admin.mailchimp.com/account/api](http://admin.mailchimp.com/account/api/ "MailChimp API").

**Setup ASIHTTPRequest**

ChimpKit is built on ASIHTTPRequest by All-Seeing Interactive. For installation instructions see [http://allseeing-i.com/ASIHTTPRequest/](http://allseeing-i.com/ASIHTTPRequest/).

**Adding ChimpKit to a project**

Create a new project in XCode. Open ChimpKit.xcodeproj and locate the ChimpKit directory. Drag this directory into your project and start using ChimpKit.
    
-------------------
    
###CKDialogController 

ChimpKit has a pre-built signup controller for easy access to your MailChimp mailing lists. This controller launches a dialog that can be used to simply gather users email addresses from within your iPhone or iPad application. All that is required is an API Key and the id for the list that you wish to use.

    #import "CKDialogController.h"
    
    [ChimpKit setAPIKey:@"<your api key>"];
    
    CKDialogController *dialog = [[CKDialogController alloc] initWithDelegate:self];

    dialog.listID     = @"<your list id>";  
    dialog.onSuccess  = @selector(signupDidSucceed:);
    dialog.onFailure  = @selector(signupDidFail:);
    [dialog show];
    
You can optionally implement a validation method on the delegate if needed.

    - (BOOL)validateEmailAddress:(NSString*)address
    {
      // Do validation stuffs
      return YES;
    }

### Accessing the API ###

ChimpKit provides a few classes for accessing the MailChimp API

    CKList
    CKCampaign 
    CKHelperMethods
    
The documentation for these classes and there methods can be found here [http://www.mailchimp.com/api/1.2/](http://www.mailchimp.com/api/1.2/). The parameters for these methods are the objective-c counterparts of the types and values described in MailChimp's API docs.
    

###License

The MIT License

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


###Credits
christopher burnett ( github.com/twoism || twoism.posterous.com )

