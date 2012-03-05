# AWS SDK set up as a Codeigniter library

I got a private message form someone asking me to help him to integrate AWS SDK as a CI library. The answer is also posted on [Stack Exchange](http://stackoverflow.com/questions/9541613/integrating-aws-sdk-as-a-library-in-codeigniter). As I have seen this similar question asked a couple of times and I didn't find any examples (for Codeigniter 2.x at least), I thought I might as well post it here for anyone else who might be interested.

AWS SDK is already included as a submodule, so all you need to do is clone it into a libraries folder of you CI application, set up the config-sample.inc.php wih your AWS credentials and you're ready to go.

Sample usage:

`public function index()
{
	$this->load->library('awslib');
	$sqs = new AmazonSQS();
	$response = $sqs->list_queues();
	var_dump($response->isOK());
}`

