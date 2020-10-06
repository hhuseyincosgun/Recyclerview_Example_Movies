# Recyclerview_Example_Movies
This project include Recyclerview example study. 
package com.hasanhuseyin.detaylirvkullanimi

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import androidx.recyclerview.widget.StaggeredGridLayoutManager
import kotlinx.android.synthetic.main.activity_main.*

class MainActivity : AppCompatActivity() {

    private lateinit var moviesArrayList: ArrayList<Movies>
    private lateinit var adapter: MovieAdapter

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        rv.setHasFixedSize(true)
        rv.layoutManager = StaggeredGridLayoutManager(2,StaggeredGridLayoutManager.VERTICAL)

        val movie1 = Movies(1,"The Fellowship of The Ring","lotr1",14.99)
        val movie2 = Movies(2,"The Two Towers","lotr2",15.99)
        val movie3 = Movies(3,"The Return of The King","lotr3",16.99)
        val movie4 = Movies(4,"An Unexpected Journey","hobbit1",11.99)
        val movie5 = Movies(5,"The Desolation of Smaug","hobbit2",12.99)
        val movie6 = Movies(6,"The Battle of the Five Armies","hobbit3",13.99)


        moviesArrayList = ArrayList<Movies>()
        moviesArrayList.add(movie1)
        moviesArrayList.add(movie2)
        moviesArrayList.add(movie3)
        moviesArrayList.add(movie4)
        moviesArrayList.add(movie5)
        moviesArrayList.add(movie6)

        adapter = MovieAdapter(this,moviesArrayList)

        rv.adapter = adapter

    }
}
