<?php

namespace Kata\Tests;


class fizzBuzzTest extends \PHPUnit_Framework_TestCase
{
    protected $fizzBuzz;

    protected function setUp()
    {
        $this->fizzBuzz = new FizzBuzz();
    }

    /**
     * @test
     */
    public function it_should_return_the_same_number()
    {
        $this->assertSame($this->fizzBuzz->play(2), 2);
    }

    /**
     * @test
     */
    public function it_should_return_fizz_when_equal_3()
    {
        $this->assertSame($this->fizzBuzz->play(3), 'fizz');
    }

    /**
     * @test
     */
    public function it_should_return_buzz_when_equal_5()
    {
        $this->assertSame($this->fizzBuzz->play(5), 'buzz');
    }

    /**
     * @test
     */
    public function it_should_return_fizz_when_multiple_of_3()
    {
        $this->assertSame($this->fizzBuzz->play(6), 'fizz');
    }

    /**
     * @test
     */
    public function it_should_return_buzz_when_multiple_of_5()
    {
        $this->assertSame($this->fizzBuzz->play(10), 'buzz');
    }

    /**
     * @test
     */
    public function it_should_return_fizzbuzz_when_multiple_of_3_and_5()
    {
        $this->assertSame($this->fizzBuzz->play(15), 'fizzbuzz');
    }

    /**
     * @test
     * @dataProvider allGameResults
     */
    public function entireGame($a ,$b)
    {
        $this->assertSame($this->fizzBuzz->play($a), $b);
    }

    /**
     * @test
     */
    public function executeGame()
    {
        $fizzbuzGame = new FizzBuzGame(new FizzBuzz());
        $this->assertSame($fizzbuzGame->execute(1, 5), '12fizz4buzz');
        $this->assertSame($fizzbuzGame->execute(80, 86), 'buzzfizz8283fizzbuzz86');
    }

    public function allGameResults()
    {
        return array(
            array(1, 1),
            array(2, 2),
            array(3, 'fizz'),
            array(30, 'fizzbuzz'),
            array(60, 'fizzbuzz'),
            array(50, 'buzz'),
            array(36, 'fizz'),
            array(99, 'fizz'),
            array(100, 'buzz'),
        );
    }

}

class FizzBuzGame
{

    private $gameRoundPlayer;

    function __construct($gameRoundPlayer)
    {
        $this->gameRoundPlayer = $gameRoundPlayer;
    }

    public function execute($start, $end)
    {
        $output = '';
        for ($i = $start; $i <= $end; $i++) {
            $output .= $this->gameRoundPlayer->play($i);
        }

        return $output;
    }
}

class FizzBuzz
{

    public function play($num)
    {
        $output = '';

        if ($this->isMultipleOfThree($num)) {
            $output .= 'fizz';
        }
        if ($this->isMultipleOfFive($num)) {
            $output .= 'buzz';
        }

        return ($output !== '') ? $output : $num;
    }

    private function isMultipleOfFive($num)
    {
        return $this->isMultipleOf($num, 5);
    }

    private function isMultipleOfThree($num)
    {
        return $this->isMultipleOf($num, 3);
    }

    private function isMultipleOf($num, $multipleOf)
    {
        return ($num % $multipleOf  === 0);
    }
}
 
