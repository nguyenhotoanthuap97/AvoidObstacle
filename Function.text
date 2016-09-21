//
//
//First Game _ Climbing
//
//
//Function.cpp

#include <stdio.h>
#include <stdlib.h>
#include "conio.h"
#include "time.h"
#include <Windows.h>

//Struct Node BOT
struct Node
{
	int x;
	int y;
	Node *pNext;
};

//struct list
struct List
{
	Node *pHead;
	Node *pTail;
};

//Ham random Xuat hien BOT
int RandomBOT()
{
	int id = 0;
	id = rand() % 3 + 1;
	switch (id)
	{
	case 1:
		return 32;
	case 2:
		return 38;
	case 3:
		return 44;
	}
}

//Ham tao Node
Node* taoNode()
{
	Node *NewNode = (Node*) malloc(sizeof(Node));
	int xN = RandomBOT();
	NewNode->x = xN;
	NewNode->pNext = NULL;
	return NewNode;
}

//Ham chen cuoi
void chenCuoi(List *L, Node *NewNode)
{
	if (L->pHead == NULL)
	{
		L->pHead = NewNode;
		L->pTail = L->pHead;
	}
	else
	{
		L->pTail->pNext = NewNode;
		L->pTail = L->pTail->pNext;
	}
}

//Ham xoa dau
void xoaDau(List *L)
{
	Node *p = NULL;
	p = L->pHead;
	L->pHead = p->pNext;
	free(p);
}

//Bien toan cuc
int Px = 38;
int Py = 22;

//Le trai: 29
//Le phai: 48

//Ham gotoxy
void gotoxy(int x, int y)
{
	HANDLE hStdout = GetStdHandle(STD_OUTPUT_HANDLE);
	COORD position = {x, y};
	SetConsoleCursorPosition(hStdout, position);
}

//Ham Duong
void Duong()
{
	for (int i = 0; i < 24; i++)
	{
		gotoxy(29, i);
		printf("%c", 177);
		gotoxy(48, i);
		printf("%c", 177);
	}
}

//Ham BOT
void BOT(int x, int y)
{
	for (int i = x - 2; i <= x + 3; i++)
	{
		for (int j = y - 1; j <= y + 1; j++)
		{
			gotoxy(i, j);
			printf("%c", 177);
		}
	}
}

//Ham Player
void Player(int x, int y)
{
	gotoxy(x, y - 1);
	printf("%c", 177);
	gotoxy(x + 1, y - 1);
	printf("%c", 177);
	gotoxy(x - 2, y);
	printf("%c", 177);
	gotoxy(x - 1, y);
	printf("%c", 177);
	gotoxy(x, y);
	printf("%c", 177);
	gotoxy(x + 1, y);
	printf("%c", 177);
	gotoxy(x + 2, y);
	printf("%c", 177);
	gotoxy(x + 3, y);
	printf("%c", 177);
	gotoxy(x + 3, y + 1);
	printf("%c", 177);
	gotoxy(x + 2, y + 1);
	printf("%c", 177);
	gotoxy(x - 1, y + 1);
	printf("%c", 177);
	gotoxy(x - 2, y + 1);
	printf("%c", 177);
}

//Ham di chuyen
int DiChuyen(char h)
{
	if (h == 75 && Px > 32)
	{
		for (int i = 21; i < 24; i++)
		{
			for (int j = Px - 2; j < Px + 4; j++)
			{
				gotoxy(j, i);
				printf(" ");
			}
		}
		Px = Px - 6;
		Player(Px, Py);
		gotoxy(Px, Py);
	}
	else if (h == 77 && Px < 43)
	{
		for (int i = 21; i < 24; i++)
		{
			for (int j = Px - 2; j < Px + 4; j++)
			{
				gotoxy(j, i);
				printf(" ");
			}
		}
		Px = Px + 6;
		Player(Px, Py);
		gotoxy(Px, Py);
	}
	return 0;
}

void gameOver()
{
	for (int i = 30; i < 48; i++)
	{
		for (int j = 9; j < 12; j++)
		{
			gotoxy(i, j);
			printf(" ");
		}
	}
	gotoxy(35, 11);
	printf("GAME OVER");
	gotoxy(29, 24);
	getch();
}

//main
void main()
{
	int id = 0;
	int ch = 0;
	int botX = 0;
	int botY = 0;
	List *L = (List*) malloc(sizeof(List));
	L->pHead = NULL;
	L->pTail = NULL;
	Node *NewNode = NULL;
	Node *Dem = NULL;
	Node *Dem2 = NULL;

	Player(Px, Py);

	srand(time(NULL));

	for (int i = 0; i < 5; i++)
	{
		NewNode = taoNode();
		chenCuoi(L, NewNode);
		Dem = L->pHead;
		while (Dem->pNext != NULL)
		{
			Dem = Dem->pNext;
		}
		Dem->y = -6 * i - 1;
	}

	Duong();

	while (1)
	{
		while (!id)
		{
			botY = L->pHead->y;
			botX = L->pHead->x;
			if (Py - 1 <= botY + 1)
			{
				if (botX - Px == 0)
				{
					gameOver();
					free(L);
					free(Dem);
					free(Dem2);
					free(NewNode);
					return;
				}
			}
			Dem = L->pHead;
			while (Dem != NULL)
			{
				botX = Dem->x;
				botY = Dem->y;
				if (botY == -1)
				{
					gotoxy(botX, botY + 1);
					printf("%c", 177);
					gotoxy(botX - 1, botY + 1);
					printf("%c", 177);
					gotoxy(botX - 2, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 1, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 2, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 3, botY + 1);
					printf("%c", 177);
				}
				else if (botY == 0)
				{
					gotoxy(botX, botY + 1);
					printf("%c", 177);
					gotoxy(botX - 1, botY + 1);
					printf("%c", 177);
					gotoxy(botX - 2, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 1, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 2, botY + 1);
					printf("%c", 177);
					gotoxy(botX + 3, botY + 1);
					printf("%c", 177);
					gotoxy(botX, botY);
					printf("%c", 177);
					gotoxy(botX - 1, botY);
					printf("%c", 177);
					gotoxy(botX - 2, botY);
					printf("%c", 177);
					gotoxy(botX + 1, botY);
					printf("%c", 177);
					gotoxy(botX + 2, botY);
					printf("%c", 177);
					gotoxy(botX + 3, botY);
					printf("%c", 177);
				}
				else if (botY > 0 && botY < 23)
				{
					BOT(botX, botY);
					if (botY - 2 >= 0)
					{
						gotoxy(botX, botY - 2);
						printf(" ");
						gotoxy(botX - 1, botY - 2);
						printf(" ");
						gotoxy(botX - 2, botY - 2);
						printf(" ");
						gotoxy(botX + 1, botY - 2);
						printf(" ");
						gotoxy(botX + 2, botY - 2);
						printf(" ");
						gotoxy(botX + 3, botY - 2);
						printf(" ");
					}
				}
				else if (botY == 23)
				{
					gotoxy(botX, botY);
					printf("%c", 177);
					gotoxy(botX - 1, botY);
					printf("%c", 177);
					gotoxy(botX - 2, botY);
					printf("%c", 177);
					gotoxy(botX + 1, botY);
					printf("%c", 177);
					gotoxy(botX + 2, botY);
					printf("%c", 177);
					gotoxy(botX + 3, botY);
					printf("%c", 177);
					gotoxy(botX, botY - 1);
					printf("%c", 177);
					gotoxy(botX - 1, botY - 1);
					printf("%c", 177);
					gotoxy(botX - 2, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 1, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 2, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 3, botY - 1);
					printf("%c", 177);
					gotoxy(botX, botY - 2);
					printf(" ");
					gotoxy(botX - 1, botY - 2);
					printf(" ");
					gotoxy(botX - 2, botY - 2);
					printf(" ");
					gotoxy(botX + 1, botY - 2);
					printf(" ");
					gotoxy(botX + 2, botY - 2);
					printf(" ");
					gotoxy(botX + 3, botY - 2);
					printf(" ");
				}
				else if (botY == 24)
				{
					gotoxy(botX, botY - 1);
					printf("%c", 177);
					gotoxy(botX - 1, botY - 1);
					printf("%c", 177);
					gotoxy(botX - 2, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 1, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 2, botY - 1);
					printf("%c", 177);
					gotoxy(botX + 3, botY - 1);
					printf("%c", 177);
					gotoxy(botX, botY - 2);
					printf(" ");
					gotoxy(botX - 1, botY - 2);
					printf(" ");
					gotoxy(botX - 2, botY - 2);
					printf(" ");
					gotoxy(botX + 1, botY - 2);
					printf(" ");
					gotoxy(botX + 2, botY - 2);
					printf(" ");
					gotoxy(botX + 3, botY - 2);
					printf(" ");
				}
				else if (botY > 24)
				{
					gotoxy(botX, botY - 2);
					printf(" ");
					gotoxy(botX - 1, botY - 2);
					printf(" ");
					gotoxy(botX - 2, botY - 2);
					printf(" ");
					gotoxy(botX + 1, botY - 2);
					printf(" ");
					gotoxy(botX + 2, botY - 2);
					printf(" ");
					gotoxy(botX + 3, botY - 2);
					printf(" ");
					xoaDau(L);
					NewNode = NULL;
					NewNode = taoNode();
					chenCuoi(L, NewNode);
					Dem2 = L->pHead;
					while (Dem2->pNext->pNext != NULL)
					{
						Dem2 = Dem2->pNext;
					}
					Dem2->pNext->y = Dem2->y - 7;
				}	
				(Dem->y)++;
				id = kbhit();
				if (id == 1)
				{
					ch = getch();
					if (ch == 224)
					{
						ch = getch();
						DiChuyen(ch);
					}
				}
				Sleep(10);
				Dem = Dem->pNext;
			}
			if (id == 1)
				id = 0;
		}
	}
}