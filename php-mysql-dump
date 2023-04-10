<?php
/**
 * @author ranesh@radus28.com
 * @internal Run this script in a LAMP / LNMP / WAMP stack server to get the MySQL backup. 
 * You may modify the code if you don't want to pass database user and password through request.
 */
ini_set('max_execution_time', 1200);
ini_set('memory_limit','1024M');
	if(!$_REQUEST['user'] && !$_REQUEST['dbPass'] && !$_REQUEST['host'] && !$_REQUEST['dbName'] && !$_REQUEST['backUpPath']){
		echo json_encode(array('success'=>false,'result' => false));
	}else{
		$user = $_REQUEST['user'];
		$password = $_REQUEST['dbPass'];
		$host = $_REQUEST['host'];
		$dbName = $_REQUEST['dbName'];
		$backUpPath = $_REQUEST['serverBackUpPath'];

		try{
			exec("mysqldump --user=$user --password=$password --host=$host $dbName | gzip > $backUpPath");
		echo json_encode(array('success'=>true,'result' => $backUpPath));
		}catch (Exception $e) {
			echo 'Caught exception: ',  $e->getMessage(), "\n";
		}
	}
?>
