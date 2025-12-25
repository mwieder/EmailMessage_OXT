EmailMessage is a library for OpenXTalk the encodes data to be sent through internet email (SMTP). EmailMessage handles all of the encoding of the message - from the headers to the different body parts and attachments.

--------------------------------------------------------------------------------------

You need to put the library in your message path by using it as a library:
	start using stack "EmailMessage"

Once the library is in use, you will need to create an instance
	put NewEmailMessage() into instance

--------------------------------------------------------------------------------------

set the header[["header"]] of <instance> to <value>
header
	name of the header:
	"FROM" sender of the email
	"TO", "CC", "BCC" comma-list of recipients to receive the message
	"REPLY-TO" who will receive any replies to this message
	"MAILER" information about the program encoding the message
	"SUBJECT" the subject of the message
	you can also create non-standard headers, but the first two characters of the header must be "X-" (without the quotes)
instance
	the long id returned from the NewEmailMessage function
value
	data associated with the header
	the following headers "FROM", "TO", "CC", "BCC", "REPLY-TO", "NOTIFY-TO" contain email addresses and an optional friendly name. If there is only an email address, then pass the email address as the value. If it has the optional friendly name pass "Name <email@example.org>" (withour the quotes).
	the following headers "TO", "CC", "BCC" may contain more than one recipient. If you are sending to more than one recipient, separate them with a comma.

--------------------------------------------------------------------------------------

set the body["<part>"] of <instance> to <value>
part
	is either "plain" or "html"
instance
	the long id returned from the NewEmailMessage function
value
	the data to be used in the part. 

--------------------------------------------------------------------------------------

set the attachment["<attachmentNumber>"] of <instance> to <path>
attachmentNumber
	a number
instance
	the long id returned from the NewEmailMessage function
path
	path to the file to be attached
