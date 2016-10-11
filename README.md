# Amazon S3 file upload using PHP 
You can download most recent version of Amazon PHP SDK by running following composer command and also can find full step by step detail on following link 
    http://phpclicks.com/amazon-s3-file-upload-using-php/

     composer require aws/aws-sdk-php

     // Include the SDK using the Composer autoloader
      require 'vendor/autoload.php';
      use Aws\S3\S3Client;
      use Aws\S3\Exception\S3Exception;

        // Set Amazon s3 credentials
      $client = S3Client::factory(
      array(
      'key'    => "your-key",
      'secret' => "your secret key"
       )
      );

        try {
        $client->putObject(array(
             'Bucket'=>'your-bucket-name',
             'Key' =>  'your-filepath-in-bucket',
             'SourceFile' => 'source-filename-with-path',
             'StorageClass' => 'REDUCED_REDUNDANCY'
        ));

    } catch (S3Exception $e) {
         // Catch an S3 specific exception.
        echo $e->getMessage();
    }
    
    
    
