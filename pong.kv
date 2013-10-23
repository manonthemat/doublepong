from kivy.app import App
from kivy.uix.widget import Widget
from kivy.properties import NumericProperty, ReferenceListProperty, ObjectProperty
from kivy.vector import Vector
from kivy.clock import Clock
from random import randint
from time import sleep


class PongGame(Widget):
    ball = ObjectProperty(None)
    player1 = ObjectProperty(None)
    player2 = ObjectProperty(None)
    player3 = ObjectProperty(None)
    player4 = ObjectProperty(None)

    def serve_ball(self, vel=(4, 0)):
        self.ball.center = self.center
#        self.ball.velocity = Vector(4, 0).rotate(randint(0, 360))
        self.ball.velocity = vel

    def update(self, dt):
        self.ball.move()

        # bounce of paddles
        # ToDo - fix this: ball doesn't bounce off a second time when paddle kept in same position
        self.player1.bounce_ball(self.ball)
        self.player2.bounce_ball(self.ball)
        self.player3.bounce_ball(self.ball)
        self.player4.bounce_ball(self.ball)

        # bounce off top and bottom
        if (self.ball.y < 0) or (self.ball.top > self.height):
            self.ball.velocity_y *= -1

        # went of to a side to score a point?
        # ToDo - fix this: player2 scores when left side of ball touches left window, but player1 scores when the left corner of ball touches the right side of the window, thus making it harder to score...
        if self.ball.x < self.x:
            self.playerScored(self.player2)
            self.serve_ball(vel=(4, 0))
        if self.ball.x > self.width:
            self.playerScored(self.player1)
            self.serve_ball(vel=(-4, 0))

    def playerScored(self, player):
        player.score += 1
        sleep(1)
        if player.score > 3:
            exit(0)

    def on_touch_move(self, touch):
        # ToDo - fix this: take paddle size into consideration
        if touch.x < self.width / 3:
            if touch.y < self.height / 2:
                self.player1.center_y = touch.y
            else:
                self.player3.center_y = touch.y
        if touch.x > self.width - self.width / 3:
            if touch.y < self.height / 2:
                self.player2.center_y = touch.y
            else:
                self.player4.center_y = touch.y


class PongBall(Widget):
    velocity_x = NumericProperty(0)
    velocity_y = NumericProperty(0)

    velocity = ReferenceListProperty(velocity_x, velocity_y)

    def move(self):
        self.pos = Vector(*self.velocity) + self.pos


class PongPaddle(Widget):
    score = NumericProperty(0)

    def bounce_ball(self, ball):
        if self.collide_widget(ball):
            vx, vy = ball.velocity
            offset = (ball.center_y - self.center_y) / (self.height / 2)
            bounced = Vector(-1 * vx, vy)
            vel = bounced * 1.1
            ball.velocity = vel.x, vel.y + offset


class PongApp(App):
    def build(self):
        game = PongGame()
        game.serve_ball()
        Clock.schedule_interval(game.update, 1.0/60.0)
        return game


if __name__ == "__main__":
    PongApp().run()

