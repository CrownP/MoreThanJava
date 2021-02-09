# Scanner

Scanner scanner = new Scanner()

1. String s = scanner.next()：碰到空格、回车、Tab键都会视为终止符
2. String s = scanner.nextLine()：碰到回车才终止输入
3. scanner.hasnext()：读取缓冲区，不空返回true，空则阻塞
4. int a = scanner.nextInt()：读取一个整数