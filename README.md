proyectoprogra

==============#include <list>
#include <curses.h>
#include <stdlib.h>
#include <time.h>


class pelota {
 private:
  int x, y;
 public:
  pelota(int a, int b) {
   x = a;
   y = b;
  }
  int getX() { return x; }
  int getY() { return y; }
};

int main() {
 srand ( time(NULL) );
 initscr();
 noecho();
 curs_set(0);
 keypad(stdscr, TRUE);
 timeout(100);

 std::list<pelota> pelotas;
 std::list<pelota>::iterator it;
 bool salir = false;
 int pts = 0;
 int direc = 2;
 int co_x = rand() % 79;
 int co_y = rand() % 24;
 char ba_x  = rand() % 79;
 char ba_y  = rand() % 24;
 char ba_x1 = rand() % 79;
 char ba_y1 = rand() % 24;
 char ba_x2 = rand() % 79;
 char ba_y2 = rand() % 24;
 char ba_x3 = rand() % 79;
 char ba_y3 = rand() % 24;
 char ba_x4 = rand() % 79;
 char ba_y4 = rand() % 24;
 char ba_x5 = rand() % 79;
 char ba_y5 = rand() % 24;
 char ba_x6 = rand() % 79;
 char ba_y6 = rand() % 24;
 char ba_x7 = rand() % 79;
 char ba_y7 = rand() % 24;
 char ba_x8 = rand() % 79;
 char ba_y8 = rand() % 24;
 char ba_x9 = rand() % 79;
 char ba_y9 = rand() % 24;
 char ba_x10 = rand() % 79;
 char ba_y10 = rand() % 24;
 char ba_x11 = rand() % 79;
 char ba_y11 = rand() % 24;
 char ba_x12 = rand() % 79;
 char ba_y12 = rand() % 24;
 char ba_x13 = rand() % 79;
 char ba_y13 = rand() % 24;
 char ba_x14 = rand() % 79;
 char ba_y14 = rand() % 24;
 char ba_x15 = rand() % 79;
 char ba_y15 = rand() % 24;
 int ch;
    for(int i = 0; i < 1; i++)
    pelotas.push_front(pelota(32+i,10));

    while(!salir) {

     ch = getch();
     switch(ch) {
     case KEY_UP:
     direc = 1;
     break;
     case KEY_RIGHT:
     direc = 2;
     break;
     case KEY_DOWN:
     direc = 3;
     break;
     case KEY_LEFT:
     direc = 4;
     break;
     case 's':
     salir = true;
     break;
     }


    pelota mov = pelotas.front();
    int x = mov.getX();
    int y = mov.getY();
    if(direc == 1) y--;
    else if(direc == 2) x++;
    else if(direc == 3) y++;
    else if(direc == 4) x--;
    pelotas.push_front(pelota(x, y));
    if(x == co_x && y == co_y) {
    co_x = rand() % 79;
    co_y = rand() % 24;
    pts++;
    if(x == ba_x && y == ba_y)
    ba_x = rand() % 79;
    ba_y = rand() % 24;
    if(x == ba_x1 && y == ba_y1)
    ba_x1 = rand()% 79;
    ba_y1 = rand()% 24;
    if(x == ba_x2 && y == ba_y2)
    ba_x2 = rand() % 79;
    ba_y2 = rand()% 24;
    if(x == ba_x3 && y == ba_y3)
    ba_x3 = rand()% 79;
    ba_y3 = rand()% 24;
    if(x == ba_x4 && y == ba_y4)
    ba_x4 = rand()% 79;
    ba_y4 = rand()% 24;
    if(x == ba_x5 && y == ba_y5)
    ba_x5 = rand()% 79;
    ba_y5 = rand()% 24;
    if(x == ba_x6 && y == ba_y6)
    ba_x6 = rand()% 79;
    ba_y6 = rand()% 24;
    if(x == ba_x7 && y == ba_y7)
    ba_x7 = rand()% 79;
    ba_y7 = rand();
    if(x == ba_x8 && y == ba_y8)
    ba_x8 = rand()% 79;
    ba_y8 = rand()% 24;
    if(x == ba_x9 && y == ba_y9)
    ba_x9 = rand()% 79;
    ba_y9 = rand()% 24;
    if(x == ba_x10 && y == ba_y10)
    ba_x10 = rand()% 79;
    ba_y10 = rand()% 24;
    if(x == ba_x11 && y == ba_y11)
    ba_x11 = rand()% 79;
    ba_y11 = rand()% 24;
    if(x == ba_x12 && y == ba_y12)
    ba_x12 = rand()% 79;
    ba_y12 = rand();
    if(x == ba_x13 && y == ba_y13)
    ba_x13 = rand()% 79;
    ba_y13 = rand()% 24;
    if(x == ba_x14 && y == ba_y14)
    ba_x14 = rand()% 79;
    ba_y14= rand()% 24;
    if(x == ba_x15 && y == ba_y15)
    ba_x15 = rand()% 79;
    ba_y15= rand()% 24;
} else
      pelotas.pop_back();
    if(y > 24 || x > 79 || y < 0 || x < 0 )
      salir = true;
      erase();
     mvaddch(ba_y,ba_x,'°');
     mvaddch(ba_y1,ba_x1,'_');
     mvaddch(ba_y2,ba_x2,'°');
     mvaddch(ba_y3,ba_x3,'-');
     mvaddch(ba_y4,ba_x4,'°');
     mvaddch(ba_y5,ba_x5,'-');
     mvaddch(ba_y6,ba_x6,'°');
     mvaddch(ba_y7,ba_x7,'-');
     mvaddch(ba_y8,ba_x8,'°');
     mvaddch(ba_y9,ba_x9,'-');
     mvaddch(ba_y10,ba_x10,'°');
     mvaddch(ba_y11,ba_x11,'-');
     mvaddch(ba_y12,ba_x12,'°');
     mvaddch(ba_y13,ba_x13,'-');
     mvaddch(ba_y14,ba_x14,'°');
     mvaddch(ba_y15,ba_x15,'-');
     mvaddch(co_y,co_x,'*');
        for(it = pelotas.begin(); it != pelotas.end(); it--) {
        mvaddch((*it).getY(),(*it).getX(),'O');
        if((*it).getY() == ba_y && (*it).getX() == ba_x )
        salir = true;
        if((*it).getY() == ba_y1 && (*it).getX() == ba_x1 )
        salir =true;
        if((*it).getY() == ba_y2 && (*it).getX() == ba_x2 )
        salir = true;
        if((*it).getY() == ba_y3 && (*it).getX() == ba_x3 )
        salir = true;
        if((*it).getY() == ba_y4 && (*it).getX() == ba_x4)
        salir = true;
        if((*it).getY() == ba_y5 && (*it).getX() == ba_x5)
        salir = true;
        if((*it).getY() == ba_y6 && (*it).getX() == ba_x6)
        salir =true;
        if((*it).getY() == ba_y7 && (*it).getX() == ba_x7)
        salir = true;
        if((*it).getY() == ba_y8 && (*it).getX() == ba_x8)
        salir = true;
        if((*it).getY() == ba_y9 && (*it).getX() == ba_x9)
        salir = true;
        if((*it).getY() == ba_y10 && (*it).getX() == ba_x10)
        salir = true;
        if((*it).getY() == ba_y11 && (*it).getX() == ba_x11)
        salir = true;
        if((*it).getY() == ba_y12 && (*it).getX() == ba_x12)
        salir = true;
        if((*it).getY() == ba_y13 && (*it).getX() == ba_x13)
        salir = true;
        if((*it).getY() == ba_y14 && (*it).getX() == ba_x14)
        salir = true;
        if((*it).getY() == ba_y15 && (*it).getX() == ba_x15)
        salir = true;
           }


     mvprintw(0, 55, " TU PUNTAJE: %i \n", pts);
     refresh();
    }
    timeout(-1);
    erase();
    mvprintw(10, 32, "Has perdido, tu puntaje fue: %i", pts);
    refresh();
    getch();
    endwin();
    return 0;
}

