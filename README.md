# Email Related Files to Creator

Utilization of the System.Net.Mail.MailMessage class within Aras Innovator can be utilized to create custom Emails to send to specific users by using a Server-Side method.

The method code provided in this sample is used to send an Email to a Document create containing all related files as attachments to the email. This method is then called from a Server Side action against the Document Item.

## History

This project and the following release notes have been migrated from the old Aras Projects page.

Release | Notes
--------|--------
[v1](https://github.com/ArasLabs/email-related-files/releases/tag/v1) | PDF Document for creating the method and action

#### Supported Aras Versions

Project | Aras
--------|------
[v1](https://github.com/ArasLabs/email-related-files/releases/tag/v1) | 9.3.0

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed
2. Aras Package Import tool
3. **ProductLineBasedWorkflow** import package

### Install Steps

Use the following steps to create a server-side (C#) method that will be called from an Item
action against the Document ItemType. Ensure that all user’s have a valid Email Address.

1. Log into Aras Innovator as an Administrator.
2. From the TOC select **Administration > Methods** and create a new Server-Side, C#
method.
    - Name=Email_files_to_creator
    - Copy the method code from [the appendix](./Documentation/Email%20Related%20Files%20to%20Creator.pdf).
3. Save, Unlock and close *Email_files_to_creator*.
4. From the TOC select **Administration > ItemTypes** and open Document for edit.
    - Select the Actions tab and Create a new action
        - Name = Email Doc to Creator
        - Type = Item
        - Location = Server
        - Method = *Email_files_to_creator*
        - Target = None
5. Save, Unlock and Close Document.

Once the action has been created you will be able to select a single document to run the
action. Execution of the action will send an HTML email to creator containing all related files
as attachments.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Credits

Created by Aras Corporation Support.

## License

Published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
