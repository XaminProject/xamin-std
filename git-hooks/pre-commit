#!/usr/bin/php
<?php
echo "pre-commit hook\n";
$staged = `git diff --staged --cached --name-status`;
$staged = explode("\n", $staged);
foreach ($staged as &$single)
	$single = explode("\t", $single);

//We have files now
foreach ($staged as $file) {
	if (count($file) != 2)
		continue;
	if($file[0] == 'D') { //Ignore deleted files
		continue;
	}
	if (preg_match("/php$/i", $file[1]) != 0) {
		$address = $file[1];
		$result = array();
		$return = 0;
		$code = exec("php -l $address", $result, $return);
		if ($return != 0 ) {
			echo "Check for file $address failed, result is : " . print_r($result, true);
			exit(1);
		}
		
		$code = exec("phpcs --standard=Xamin $address", $result, $return);
		if ($return != 0 ) {
			echo "Codesniffer check on $address failed, result is : " . print_r($result, true);
			exit(1);
		}	
		//Now check for some things in file, like var_dump and xdebug_break
		$invalidKeys = array (
			'xdebug_break',
			'var_dump',
			'print_r',
			);

		foreach ($invalidKeys as $key) {
			$result = array();
			$return = 0;
			exec("grep -iHn $key $address", $result, $return);
			if ($return ==0) {
				echo "Found invalid keyword : " . print_r($result, true);
				exit(1);
			}
		}
	} elseif (preg_match("/js$/i", $file[1]) != 0) {
		$address = $file[1];
		$result = array();
		$return = 0;
		$code = exec("jshint $address", $result, $return);
		if ($return != 0 ) {
			echo "Check for file $address failed, result is : " . print_r($result, true);
			exit(1);
		}
	}
}

exit(0);
