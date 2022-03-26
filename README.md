
# store-config-server
# local project set

# github local set
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server
	$ echo "# store-config-server" >> README.md
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server
	$ git init
	Initialized empty Git repository in C:/Users/lsv40/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server/.git/
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ git add README.md
	warning: LF will be replaced by CRLF in README.md.
	The file will have its original line endings in your working directory
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ git commit -m "first commit"
	[master (root-commit) 46416cd] first commit
	 1 file changed, 55 insertions(+)
	 create mode 100644 README.md
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (master)
	$ git branch -M main
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (main)
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (main)
	$ git remote add origin https://github.com/sangbinlee/store-config-server.git
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (main)
	$ 
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (main)
	$ git push -u origin main
	Enumerating objects: 3, done.
	Counting objects: 100% (3/3), done.
	Delta compression using up to 12 threads
	Compressing objects: 100% (2/2), done.
	Writing objects: 100% (3/3), 703 bytes | 703.00 KiB/s, done.
	Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
	To https://github.com/sangbinlee/store-config-server.git
	 * [new branch]      main -> main
	Branch 'main' set up to track remote branch 'main' from 'origin'.
	
	lsv40@DESKTOP-UFPDSPR MINGW64 ~/Documents/workspace-spring-tool-suite-4-4.14.0.RELEASE/store-config-server (main)
	$
	
		
# github desktop - push# store-config-server



# test url
	http://localhost:9999/config/prod	
	http://localhost:9999/config/dev	
	
	
	http://localhost:9999/config/store-prod
	http://localhost:9999/config/store-dev
	
	

# config server 가 바라보는 설정정보 위치
	https://github.com/sangbinlee/store-config-files.git
	
# config client 가 바라보는 설정정보 위치	
	@Value("${sodi.store.info}")//  git yml key
	
		
	server:
	  port: 8088
	  
	---
	spring:
	  application:
	    name: config-store-dev
	  config:
	    import: optional:configserver:http://localhost:9999
	# test:
	#   str: test-str
	
	# actuator lib set
	management:
	  endpoints:
	    web:
	      exposure:
	        include: refresh, health, beans	
	        
# TODO 	        
	# config client 는 각각 msa
	# 모든 msa 는 config client 로 config server를 통해서 git의 설정정보를 가져온다.
	
	# 설정정보를 각 msa는 전역 변수 로 가지고 있어야 하고 그 정보는 암호화 되어있고 
	사용시 복호화 되어야 함.	        