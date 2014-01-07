# NAME

Audio::Play::MPlayer - a frontend to play audio files using MPlayer

# SYNOPSIS

    use Audio::Play::MPlayer;

    # same as Audio::Play::MPG123
    $player = Audio::Play::MPlayer->new;
    $player->load( "ex-mp30.mp3" );
    print $player->title, "\n";
    $player->poll( 1 ) until $player->state == 0;

# DESCRIPTION

This module acts as a frontend to an external MPlayer process started
with the `-slave` command-line option.  The idea and interface (and
in part the code) has been taken from [Audio::Play::MPG123](http://search.cpan.org/perldoc?Audio::Play::MPG123).

Please see [Audio::Play::MPG123](http://search.cpan.org/perldoc?Audio::Play::MPG123) for the documentation.  Take into account
that the methods:

    copyrighted
    emphasis
    error_protected
    extension
    layer
    mode
    mode_extension
    stat
    statfreq
    type
    url
    IN

have not been implemented, and that:

    jump
    tpf

work differently: `jump` takes offsets in seconds, and `tpf` always
returns `1` to make it possible to write:

    $player->jump( 60 / $player->tpf );

# AUTHOR

Mattia Barbon <mbarbon@cpan.org>, using ideas from
[Audio::Play::MPG123](http://search.cpan.org/perldoc?Audio::Play::MPG123) by Marc Lehmann <schmorp@schmorp.de>.

# LICENSE

This program is free software; you can redistribute it and/or
modify it under the same terms as Perl itself.

# SOURCES

The latest sources can be found on GitHub at
[http://github.com/mbarbon/audio-play-mplayer/tree](http://github.com/mbarbon/audio-play-mplayer/tree)

# THANKS

Marc Lehmann <schmorp@schmorp.de> for [Audio::Play::MPG123](http://search.cpan.org/perldoc?Audio::Play::MPG123).

The MP3 file used in tests has been taken from
[http://www.shellworld.net/~davidsky/exam-mp3.htm](http://www.shellworld.net/~davidsky/exam-mp3.htm) (test ID3 tag not
in original).