(1)��ʼ��һ���ֿ�
	git init
(2)����ļ����ֿ�
	git add <file1,file2,...>
	git commit -m <message>
(3)�鿴������״̬
	git status
(4)�鿴�ļ��޸����
	git diff <file>
(5)�汾����
	git reset --hard <commit_id>	����أ�HEAD^,HEAD^^,...
(6)�鿴�汾��ʷ
	git log
(7)�鿴������ʷ
	git reflog
(8)�������������޸�,�ص����һ��git commit��git addʱ��״̬
	git checkout -- <file>
(9)���ļ������ݴ���
	git reset HEAD <file>
(10)�Ӱ汾����ɾ���ļ�
	git rm <file>(�������Ѿ���ɾ���ļ���Ҳ����git add <file>)
	git commit -m <message>
(11)����SSH Key
	ssh-keygen -t rsa -C "<email>"
(12)���Զ�̿�
	��������github���������У�֮��ʹ��git push -u origin master������
(13)��¡Զ�̿�
	�Ƚ���github����ֿ⣬Ȼ��ʹ��git clone git@github.com:qymeng/<�ֿ���>.git
