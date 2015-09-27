# SDL_Pango

This project is a lightweight rewrite of
[SDL_Pango](http://sdlpango.sourceforge.net/) to work with SDL2. The
code is much shorter and provides almost similar functionality.

# Documentation

See the implemented APIs in the header file `SDL_Pango.h` and their
[documentation](http://sdlpango.sourceforge.net/_s_d_l___pango_8c.html) on the
original SDL_Pango project.

# Different API from SDL_Pango

There are two new methods to replace `SDLPango_SetDefaultColor` and the removed
`SDLPango_Matrix` which allows you to specify the text color:

    void
    SDLPango_SetColor(SDLPango_Context* context,
                      const SDL_Color* color);

    SDL_Color
    SDLPango_GetColor(SDLPango_Context* context);

# Known issues

* Only the fundamental SDL_Pango's original project APIs are rewritten.
* ~~There is a tiny black border around the white letters on non-black
background and vice versa, which could be solved by changing SDL blending mode
using `SDL_SetSurfaceBlendMode(surface, SDL_BLENDMODE_MOD)` or
`SDL_SetSurfaceBlendMode(surface, SDL_BLENDMODE_ADD)`~~.
