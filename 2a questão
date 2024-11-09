% 2a questão
% Definição das variáveis aleatórias
random_variable(str, ['dry', 'wet', 'snow_covered']).
random_variable(flw, [t, f]).
random_variable(r, [t, f]).
random_variable(v, [t, f]).
random_variable(b, [t, f]).
random_variable(k, [t, f]).
random_variable(li, [t, f]).

% Probabilidades a priori
0.6::str('dry').
0.3::str('wet').
0.1::str('snow_covered').
0.2::flw(t).
0.8::flw(f).
0.95::b(t).
0.05::b(f).
0.98::k(t).
0.02::k(f).

% Probabilidades condicionais
0.1::r(t) :- str('dry'), flw(t).
0.05::r(t) :- str('dry'), flw(f).
0.3::r(t) :- str('wet'), flw(t).
0.1::r(t) :- str('wet'), flw(f).
0.5::r(t) :- str('snow_covered'), flw(t).
0.2::r(t) :- str('snow_covered'), flw(f).

0.9::v(t) :- r(t).
0.2::v(t) :- r(f).

0.99::li(t) :- v(t), b(t), k(t).
0.01::li(t) :- v(t), b(t), k(f).
0.01::li(t) :- v(t), b(f), k(t).
0.001::li(t) :- v(t), b(f), k(f).
0.3::li(t) :- v(f), b(t), k(t).
0.005::li(t) :- v(f), b(t), k(f).
0.005::li(t) :- v(f), b(f), k(t).
0.0::li(t) :- v(f), b(f), k(f).

% Consulta
query(v).
evidence(str('snow_covered')).
